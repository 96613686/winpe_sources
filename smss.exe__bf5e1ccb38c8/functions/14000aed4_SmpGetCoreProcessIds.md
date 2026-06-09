# SmpGetCoreProcessIds

- ea: `0x14000aed4`
- end: `0x14000af64`
- name: `SmpGetCoreProcessIds`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140005f64`

## callees

- `0x14000aed4`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x14000af52`
- `ntdll!RtlReleaseSRWLockShared` at `0x14000af52`
- `ntdll!RtlAcquireSRWLockShared` at `0x14000aef9`
- `ntdll!RtlAcquireSRWLockShared` at `0x14000aef9`
- `ntdll!RtlSleepConditionVariableSRW` at `0x14000af11`
- `ntdll!RtlSleepConditionVariableSRW` at `0x14000af11`

## pseudocode

```c
__int64 __fastcall SmpGetCoreProcessIds(unsigned int a1, _QWORD *a2)
{
  __int64 v3; // rbx
  unsigned int v4; // edi
  __int64 v5; // rcx
  volatile signed __int32 *v6; // rdx

  v3 = SmpCoreProcessIds + 40LL * a1;
  RtlAcquireSRWLockShared(v3 + 8);
  while ( !*(_DWORD *)(v3 + 4) )
    RtlSleepConditionVariableSRW(v3 + 16, v3 + 8, 0, 1);
  if ( *(_QWORD *)(v3 + 32) )
  {
    v4 = 0;
    v5 = 0;
    do
    {
      while ( 1 )
      {
        v6 = *(volatile signed __int32 **)(v3 + 8 * v5 + 24);
        a2[v5] = v6;
        if ( (_DWORD)v5 || !*a2 )
          break;
        _InterlockedIncrement(v6);
        v5 = 1;
      }
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < 2 );
  }
  else
  {
    v4 = -1073741823;
  }
  RtlReleaseSRWLockShared(v3 + 8);
  return v4;
}

```

## disassembly

```asm
0x14000aed4  push    rbx
0x14000aed6  push    rsi
0x14000aed7  push    rdi
0x14000aed8  push    r14
0x14000aeda  sub     rsp, 28h
0x14000aede  mov     eax, ecx
0x14000aee0  mov     r14, rdx
0x14000aee3  lea     rcx, [rax+rax*4]
0x14000aee7  mov     rax, cs:SmpCoreProcessIds
0x14000aeee  lea     rbx, [rax+rcx*8]
0x14000aef2  lea     rsi, [rbx+8]
0x14000aef6  mov     rcx, rsi
0x14000aef9  call    cs:__imp_RtlAcquireSRWLockShared
0x14000aeff  jmp     short loc_14000AF17
0x14000af01  mov     r9d, 1
0x14000af07  lea     rcx, [rbx+10h]
0x14000af0b  xor     r8d, r8d
0x14000af0e  mov     rdx, rsi
0x14000af11  call    cs:__imp_RtlSleepConditionVariableSRW
0x14000af17  cmp     dword ptr [rbx+4], 0
0x14000af1b  jz      short loc_14000AF01
0x14000af1d  cmp     qword ptr [rbx+20h], 0
0x14000af22  jnz     short loc_14000AF2B
0x14000af24  mov     edi, 0C0000001h
0x14000af29  jmp     short loc_14000AF4F
0x14000af2b  xor     edi, edi
0x14000af2d  xor     ecx, ecx
0x14000af2f  mov     rdx, [rbx+rcx*8+18h]
0x14000af34  mov     [r14+rcx*8], rdx
0x14000af38  test    ecx, ecx
0x14000af3a  jnz     short loc_14000AF48
0x14000af3c  cmp     [r14], rdi
0x14000af3f  jz      short loc_14000AF48
0x14000af41  lock inc dword ptr [rdx]
0x14000af44  inc     ecx
0x14000af46  jmp     short loc_14000AF2F
0x14000af48  inc     ecx
0x14000af4a  cmp     ecx, 2
0x14000af4d  jb      short loc_14000AF2F
0x14000af4f  mov     rcx, rsi
0x14000af52  call    cs:__imp_RtlReleaseSRWLockShared
0x14000af58  mov     eax, edi
0x14000af5a  add     rsp, 28h
0x14000af5e  pop     r14
0x14000af60  pop     rdi
0x14000af61  pop     rsi
0x14000af62  pop     rbx
0x14000af63  retn
```
