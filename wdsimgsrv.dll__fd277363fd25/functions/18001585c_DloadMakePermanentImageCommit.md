# DloadMakePermanentImageCommit

- ea: `0x18001585c`
- end: `0x180015920`
- name: `DloadMakePermanentImageCommit`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800159c8`

## callees

- `0x18001585c`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x1800158bb`
- `KERNEL32!GetSystemInfo` at `0x1800158bb`
- `KERNEL32!VirtualQuery` at `0x180015899`
- `KERNEL32!VirtualQuery` at `0x180015899`

## pseudocode

```c
SIZE_T __fastcall DloadMakePermanentImageCommit(unsigned __int64 a1, unsigned __int64 a2)
{
  SIZE_T result; // rax
  __int64 dwPageSize; // r9
  volatile signed __int32 *v6; // r8
  unsigned __int64 v7; // rcx
  struct _MEMORY_BASIC_INFORMATION v8; // [rsp+20h] [rbp-68h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-38h] BYREF

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
0x18001585c  mov     rax, rsp
0x18001585f  mov     [rax+8], rbx
0x180015863  push    rdi
0x180015864  sub     rsp, 80h
0x18001586b  xorps   xmm0, xmm0
0x18001586e  xorps   xmm1, xmm1
0x180015871  mov     rdi, rdx
0x180015874  mov     r8d, 30h ; '0'; dwLength
0x18001587a  lea     rdx, [rax-68h]; lpBuffer
0x18001587e  mov     rbx, rcx
0x180015881  movups  xmmword ptr [rax-68h], xmm0
0x180015885  movups  xmmword ptr [rax-58h], xmm0
0x180015889  movups  xmmword ptr [rax-48h], xmm0
0x18001588d  movups  xmmword ptr [rax-38h], xmm1
0x180015891  movups  xmmword ptr [rax-28h], xmm1
0x180015895  movups  xmmword ptr [rax-18h], xmm1
0x180015899  call    cs:__imp_VirtualQuery
0x1800158a0  nop     dword ptr [rax+rax+00h]
0x1800158a5  test    rax, rax
0x1800158a8  jnz     short loc_1800158AF
0x1800158aa  lea     ecx, [rax+19h]
0x1800158ad  int     29h; Win8: RtlFailFast(ecx)
0x1800158af  test    [rsp+88h+var_44], 44h
0x1800158b4  jz      short loc_18001590E
0x1800158b6  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x1800158bb  call    cs:__imp_GetSystemInfo
0x1800158c2  nop     dword ptr [rax+rax+00h]
0x1800158c7  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x1800158cc  xor     edx, edx
0x1800158ce  mov     r8d, r9d
0x1800158d1  neg     r8
0x1800158d4  and     r8, rbx
0x1800158d7  lea     ecx, [r9-1]
0x1800158db  mov     eax, ecx
0x1800158dd  and     ecx, ebx
0x1800158df  and     eax, edi
0x1800158e1  add     eax, ecx
0x1800158e3  dec     rax
0x1800158e6  add     rax, r9
0x1800158e9  div     r9
0x1800158ec  xor     edx, edx
0x1800158ee  mov     rcx, rax
0x1800158f1  mov     rax, rdi
0x1800158f4  div     r9
0x1800158f7  add     rcx, rax
0x1800158fa  mov     eax, ecx
0x1800158fc  test    ecx, ecx
0x1800158fe  jz      short loc_18001590E
0x180015900  lock or dword ptr [r8], 0
0x180015905  add     r8, r9
0x180015908  sub     rax, 1
0x18001590c  jnz     short loc_180015900
0x18001590e  mov     rbx, [rsp+88h+arg_0]
0x180015916  add     rsp, 80h
0x18001591d  pop     rdi
0x18001591e  retn
```
