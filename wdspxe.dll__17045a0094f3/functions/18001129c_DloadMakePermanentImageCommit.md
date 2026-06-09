# DloadMakePermanentImageCommit

- ea: `0x18001129c`
- end: `0x180011360`
- name: `DloadMakePermanentImageCommit`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011368`

## callees

- `0x18001129c`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x1800112d9`
- `KERNEL32!VirtualQuery` at `0x1800112d9`
- `KERNEL32!GetSystemInfo` at `0x1800112fb`
- `KERNEL32!GetSystemInfo` at `0x1800112fb`

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
        + (unsigned __int64)(((unsigned int)a1 & (SystemInfo.dwPageSize - 1))
                           + ((unsigned int)a2 & (SystemInfo.dwPageSize - 1)))
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
0x18001129c  mov     rax, rsp
0x18001129f  mov     [rax+8], rbx
0x1800112a3  push    rdi
0x1800112a4  sub     rsp, 80h
0x1800112ab  xorps   xmm0, xmm0
0x1800112ae  xorps   xmm1, xmm1
0x1800112b1  mov     rdi, rdx
0x1800112b4  mov     r8d, 30h ; '0'; dwLength
0x1800112ba  lea     rdx, [rax-68h]; lpBuffer
0x1800112be  mov     rbx, rcx
0x1800112c1  movups  xmmword ptr [rax-68h], xmm0
0x1800112c5  movups  xmmword ptr [rax-58h], xmm0
0x1800112c9  movups  xmmword ptr [rax-48h], xmm0
0x1800112cd  movups  xmmword ptr [rax-38h], xmm1
0x1800112d1  movups  xmmword ptr [rax-28h], xmm1
0x1800112d5  movups  xmmword ptr [rax-18h], xmm1
0x1800112d9  call    cs:__imp_VirtualQuery
0x1800112e0  nop     dword ptr [rax+rax+00h]
0x1800112e5  test    rax, rax
0x1800112e8  jnz     short loc_1800112EF
0x1800112ea  lea     ecx, [rax+19h]
0x1800112ed  int     29h; Win8: RtlFailFast(ecx)
0x1800112ef  test    [rsp+88h+var_44], 44h
0x1800112f4  jz      short loc_18001134E
0x1800112f6  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x1800112fb  call    cs:__imp_GetSystemInfo
0x180011302  nop     dword ptr [rax+rax+00h]
0x180011307  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x18001130c  xor     edx, edx
0x18001130e  mov     r8d, r9d
0x180011311  neg     r8
0x180011314  and     r8, rbx
0x180011317  lea     ecx, [r9-1]
0x18001131b  mov     eax, ecx
0x18001131d  and     ecx, ebx
0x18001131f  and     eax, edi
0x180011321  add     eax, ecx
0x180011323  dec     rax
0x180011326  add     rax, r9
0x180011329  div     r9
0x18001132c  xor     edx, edx
0x18001132e  mov     rcx, rax
0x180011331  mov     rax, rdi
0x180011334  div     r9
0x180011337  add     rcx, rax
0x18001133a  mov     eax, ecx
0x18001133c  test    ecx, ecx
0x18001133e  jz      short loc_18001134E
0x180011340  lock or dword ptr [r8], 0
0x180011345  add     r8, r9
0x180011348  sub     rax, 1
0x18001134c  jnz     short loc_180011340
0x18001134e  mov     rbx, [rsp+88h+arg_0]
0x180011356  add     rsp, 80h
0x18001135d  pop     rdi
0x18001135e  retn
```
