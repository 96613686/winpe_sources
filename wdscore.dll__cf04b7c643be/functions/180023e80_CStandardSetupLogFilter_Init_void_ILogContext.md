# CStandardSetupLogFilter::Init(void *,ILogContext *)

- ea: `0x180023e80`
- end: `0x180023f73`
- name: `?Init@CStandardSetupLogFilter@@UEAA?AW4tagLOGRESULT@@PEAXPEAVILogContext@@@Z`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180023e80`
- `0x180025480`
- `0x180027510`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180023ec2`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180023ec2`

## pseudocode

```c
__int64 __fastcall CStandardSetupLogFilter::Init(_DWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v7; // rax
  _DWORD v8[4]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  v8[0] = 0;
  if ( (_WORD)g_DebugInf == 63 )
  {
    if ( GetWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
      return 0;
    LOWORD(g_DebugInf) = Buffer[0];
  }
  if ( !a2 )
    return 1;
  if ( *(_QWORD *)a2 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)a3 + 40LL))(a3, *(_QWORD *)a2, v8) )
    {
      a1[2] = v8[0];
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 48LL))(a3);
      if ( v7 )
      {
        if ( *(_DWORD *)(v7 + 520) == 1 && (unsigned int)pIsLogSeverityCorrect(*(_DWORD *)(a2 + 8), 0) )
        {
          a1[3] = *(_DWORD *)(a2 + 8);
          a1[4] = *(_DWORD *)(a2 + 16);
          a1[5] = *(_DWORD *)(a2 + 12);
          return 1;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180023e80  push    rbx
0x180023e82  push    rsi
0x180023e83  push    rdi
0x180023e84  sub     rsp, 250h
0x180023e8b  mov     rax, cs:__security_cookie
0x180023e92  xor     rax, rsp
0x180023e95  mov     [rsp+268h+var_28], rax
0x180023e9d  cmp     cs:?g_DebugInf@@3PAGA, 3Fh ; '?'; ushort near * g_DebugInf
0x180023ea5  mov     rsi, r8
0x180023ea8  mov     rbx, rdx
0x180023eab  mov     [rsp+268h+var_248], 0
0x180023eb3  mov     rdi, rcx
0x180023eb6  jnz     short loc_180023EE3
0x180023eb8  mov     edx, 104h; uSize
0x180023ebd  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x180023ec2  call    cs:__imp_GetWindowsDirectoryW
0x180023ec9  nop     dword ptr [rax+rax+00h]
0x180023ece  dec     eax
0x180023ed0  cmp     eax, 102h
0x180023ed5  ja      short loc_180023F55
0x180023ed7  movzx   eax, [rsp+268h+Buffer]
0x180023edc  mov     cs:?g_DebugInf@@3PAGA, ax; ushort near * g_DebugInf
0x180023ee3  test    rbx, rbx
0x180023ee6  jnz     short loc_180023EEF
0x180023ee8  mov     eax, 1
0x180023eed  jmp     short loc_180023F57
0x180023eef  mov     rdx, [rbx]
0x180023ef2  test    rdx, rdx
0x180023ef5  jz      short loc_180023F55
0x180023ef7  mov     rax, [rsi]
0x180023efa  lea     r8, [rsp+268h+var_248]
0x180023eff  mov     rcx, rsi
0x180023f02  mov     rax, [rax+28h]
0x180023f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f0b  test    eax, eax
0x180023f0d  jz      short loc_180023F55
0x180023f0f  mov     edx, [rsp+268h+var_248]
0x180023f13  mov     rcx, rsi
0x180023f16  mov     [rdi+8], edx
0x180023f19  mov     rax, [rsi]
0x180023f1c  mov     rax, [rax+30h]
0x180023f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f25  test    rax, rax
0x180023f28  jz      short loc_180023F55
0x180023f2a  cmp     dword ptr [rax+208h], 1
0x180023f31  jnz     short loc_180023F55
0x180023f33  mov     ecx, [rbx+8]; unsigned int
0x180023f36  xor     edx, edx; int *
0x180023f38  call    ?pIsLogSeverityCorrect@@YAHKPEAH@Z; pIsLogSeverityCorrect(ulong,int *)
0x180023f3d  test    eax, eax
0x180023f3f  jz      short loc_180023F55
0x180023f41  mov     eax, [rbx+8]
0x180023f44  mov     [rdi+0Ch], eax
0x180023f47  mov     eax, [rbx+10h]
0x180023f4a  mov     [rdi+10h], eax
0x180023f4d  mov     eax, [rbx+0Ch]
0x180023f50  mov     [rdi+14h], eax
0x180023f53  jmp     short loc_180023EE8
0x180023f55  xor     eax, eax
0x180023f57  mov     rcx, [rsp+268h+var_28]
0x180023f5f  xor     rcx, rsp; StackCookie
0x180023f62  call    __security_check_cookie
0x180023f67  add     rsp, 250h
0x180023f6e  pop     rdi
0x180023f6f  pop     rsi
0x180023f70  pop     rbx
0x180023f71  retn
```
