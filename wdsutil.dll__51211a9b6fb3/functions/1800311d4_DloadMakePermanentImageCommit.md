# DloadMakePermanentImageCommit

- ea: `0x1800311d4`
- end: `0x180031298`
- name: `DloadMakePermanentImageCommit`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800312a0`

## callees

- `0x1800311d4`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x180031233`
- `KERNEL32!GetSystemInfo` at `0x180031233`
- `KERNEL32!VirtualQuery` at `0x180031211`
- `KERNEL32!VirtualQuery` at `0x180031211`

## pseudocode

```c
SIZE_T __fastcall DloadMakePermanentImageCommit(unsigned __int64 a1, unsigned __int64 a2)
{
  SIZE_T result; // rax
  __int64 dwPageSize; // r9
  volatile signed __int32 *v6; // r8
  unsigned __int64 v7; // rcx
  struct _MEMORY_BASIC_INFORMATION v8; // [rsp+20h] [rbp-68h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-38h] BYREF

  memset(&v8, 0, sizeof(v8));
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  result = VirtualQuery((LPCVOID)a1, &v8, 0x30u);
  if ( !result )
    __fastfail(0x19u);
  if ( (v8.Protect & 0x44) != 0 )
  {
    GetSystemInfo(&SystemInfo);
    dwPageSize = SystemInfo.dwPageSize;
    v6 = (volatile signed __int32 *)(a1 & -(__int64)SystemInfo.dwPageSize);
    v7 = a2 / SystemInfo.dwPageSize
       + (SystemInfo.dwPageSize
        + (unsigned __int64)(((SystemInfo.dwPageSize - 1) & (unsigned int)a1)
                           + ((SystemInfo.dwPageSize - 1) & (unsigned int)a2))
        - 1)
       / SystemInfo.dwPageSize;
    for ( result = (unsigned int)v7; result; --result )
    {
      _InterlockedOr(v6, 0);
      v6 = (volatile signed __int32 *)((char *)v6 + dwPageSize);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800311d4  mov     rax, rsp
0x1800311d7  mov     [rax+8], rbx
0x1800311db  push    rdi
0x1800311dc  sub     rsp, 80h
0x1800311e3  xorps   xmm0, xmm0
0x1800311e6  xorps   xmm1, xmm1
0x1800311e9  mov     rdi, rdx
0x1800311ec  mov     r8d, 30h ; '0'; dwLength
0x1800311f2  lea     rdx, [rax-68h]; lpBuffer
0x1800311f6  mov     rbx, rcx
0x1800311f9  movups  xmmword ptr [rax-68h], xmm0
0x1800311fd  movups  xmmword ptr [rax-58h], xmm0
0x180031201  movups  xmmword ptr [rax-48h], xmm0
0x180031205  movups  xmmword ptr [rax-38h], xmm1
0x180031209  movups  xmmword ptr [rax-28h], xmm1
0x18003120d  movups  xmmword ptr [rax-18h], xmm1
0x180031211  call    cs:__imp_VirtualQuery
0x180031218  nop     dword ptr [rax+rax+00h]
0x18003121d  test    rax, rax
0x180031220  jnz     short loc_180031227
0x180031222  lea     ecx, [rax+19h]
0x180031225  int     29h; Win8: RtlFailFast(ecx)
0x180031227  test    [rsp+88h+var_44], 44h
0x18003122c  jz      short loc_180031286
0x18003122e  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180031233  call    cs:__imp_GetSystemInfo
0x18003123a  nop     dword ptr [rax+rax+00h]
0x18003123f  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x180031244  xor     edx, edx
0x180031246  mov     eax, edi
0x180031248  mov     r8d, r9d
0x18003124b  neg     r8
0x18003124e  and     r8, rbx
0x180031251  lea     ecx, [r9-1]
0x180031255  and     eax, ecx
0x180031257  and     ebx, ecx
0x180031259  add     eax, ebx
0x18003125b  dec     rax
0x18003125e  add     rax, r9
0x180031261  div     r9
0x180031264  xor     edx, edx
0x180031266  mov     rcx, rax
0x180031269  mov     rax, rdi
0x18003126c  div     r9
0x18003126f  add     rcx, rax
0x180031272  mov     eax, ecx
0x180031274  test    ecx, ecx
0x180031276  jz      short loc_180031286
0x180031278  lock or dword ptr [r8], 0
0x18003127d  add     r8, r9
0x180031280  sub     rax, 1
0x180031284  jnz     short loc_180031278
0x180031286  mov     rbx, [rsp+88h+arg_0]
0x18003128e  add     rsp, 80h
0x180031295  pop     rdi
0x180031296  retn
```
