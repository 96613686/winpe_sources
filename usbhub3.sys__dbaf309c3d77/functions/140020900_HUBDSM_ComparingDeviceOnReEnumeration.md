# HUBDSM_ComparingDeviceOnReEnumeration

- ea: `0x140020900`
- end: `0x1400209c4`
- name: `HUBDSM_ComparingDeviceOnReEnumeration`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400067ac`
- `0x140020900`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140020934`
- `ntoskrnl!RtlCompareMemory` at `0x140020965`
- `ntoskrnl!RtlCompareMemory` at `0x140020934`
- `ntoskrnl!RtlCompareMemory` at `0x140020965`

## pseudocode

```c
__int64 __fastcall HUBDSM_ComparingDeviceOnReEnumeration(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v2; // ebx
  const void *v3; // rcx
  int v4; // edx
  int v5; // r9d

  v1 = *(_QWORD *)(a1 + 960);
  v2 = 4089;
  v3 = (const void *)(v1 + 1740);
  if ( (*(_DWORD *)(v1 + 2472) & 4) != 0 )
  {
    if ( RtlCompareMemory(v3, (const void *)(v1 + 2544), 0x12u) != 18 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v5 = 41;
LABEL_8:
        LOBYTE(v4) = 4;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
          v4,
          5,
          v5,
          (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
        return 4061;
      }
      return 4061;
    }
  }
  else if ( RtlCompareMemory(v3, (const void *)(v1 + 1996), 0x12u) != 18 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v5 = 42;
      goto LABEL_8;
    }
    return 4061;
  }
  return v2;
}

```

## disassembly

```asm
0x140020900  mov     [rsp+arg_0], rbx
0x140020905  push    rdi
0x140020906  sub     rsp, 30h
0x14002090a  mov     rdi, [rcx+3C0h]
0x140020911  mov     ebx, 0FF9h
0x140020916  mov     r8d, 12h; Length
0x14002091c  mov     eax, [rdi+9A8h]
0x140020922  lea     rcx, [rdi+6CCh]; Source1
0x140020929  test    al, 4
0x14002092b  jz      short loc_14002095E
0x14002092d  lea     rdx, [rdi+9F0h]; Source2
0x140020934  call    cs:__imp_RtlCompareMemory
0x14002093b  nop     dword ptr [rax+rax+00h]
0x140020940  cmp     rax, 12h
0x140020944  jz      short loc_1400209B6
0x140020946  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002094d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020954  jz      short loc_1400209B1
0x140020956  mov     r9d, 29h ; ')'
0x14002095c  jmp     short loc_14002098D
0x14002095e  lea     rdx, [rdi+7CCh]; Source2
0x140020965  call    cs:__imp_RtlCompareMemory
0x14002096c  nop     dword ptr [rax+rax+00h]
0x140020971  cmp     rax, 12h
0x140020975  jz      short loc_1400209B6
0x140020977  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002097e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020985  jz      short loc_1400209B1
0x140020987  mov     r9d, 2Ah ; '*'
0x14002098d  mov     rcx, [rdi+8]
0x140020991  lea     rax, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x140020998  mov     r8d, 5
0x14002099e  mov     [rsp+38h+var_18], rax
0x1400209a3  mov     dl, 4
0x1400209a5  mov     rcx, [rcx+598h]
0x1400209ac  call    WPP_RECORDER_SF_
0x1400209b1  mov     ebx, 0FDDh
0x1400209b6  mov     eax, ebx
0x1400209b8  mov     rbx, [rsp+38h+arg_0]
0x1400209bd  add     rsp, 30h
0x1400209c1  pop     rdi
0x1400209c2  retn
```
