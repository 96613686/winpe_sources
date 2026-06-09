# CSlotListShort::FInit(unsigned __int64,ISlotList * *,IHashTbl * *,unsigned __int64)

- ea: `0x383858630`
- end: `0x3838586f8`
- name: `?FInit@CSlotListShort@@UEAAH_KPEAPEAVISlotList@@PEAPEAVIHashTbl@@0@Z`
- size: `200`
- prototype: `__int64 __fastcall(CSlotListShort *__hidden this, unsigned __int64, struct ISlotList **, struct IHashTbl **, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x3838435e0`
- `0x383858630`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x3838f4d5a`
- `KERNEL32!VirtualFree` at `0x3838f4d5a`
- `KERNEL32!VirtualAlloc` at `0x38389a307`
- `KERNEL32!VirtualAlloc` at `0x38389a341`
- `KERNEL32!VirtualAlloc` at `0x3838f4da6`
- `KERNEL32!VirtualAlloc` at `0x38389a307`
- `KERNEL32!VirtualAlloc` at `0x38389a341`
- `KERNEL32!VirtualAlloc` at `0x3838f4da6`
- `KERNEL32!InterlockedPopEntrySList` at `0x38385865f`
- `KERNEL32!InterlockedPopEntrySList` at `0x38385865f`

## pseudocode

```c
__int64 __fastcall CSlotListShort::FInit(
        CSlotListShort *this,
        unsigned __int64 a2,
        struct ISlotList **a3,
        struct IHashTbl **a4)
{
  struct CReservedBlockManager *v4; // rbp
  PSLIST_ENTRY v9; // rdi
  struct _SLIST_ENTRY *Next; // rax
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rcx
  bool v13; // cc
  size_t v14; // r8
  void *v16; // rax
  unsigned __int64 v17; // rcx
  struct _SLIST_ENTRY *v18; // rbp
  struct _SLIST_ENTRY *v19; // rax
  SIZE_T v20; // rbp

  v4 = CReservedBlockManager::s_pInstance;
  v9 = InterlockedPopEntrySList((PSLIST_HEADER)CReservedBlockManager::s_pInstance + 1);
  if ( !v9 )
  {
    v16 = VirtualAlloc(0, *(unsigned int *)v4, 0x2000u, 4u);
    if ( !v16 )
      return 0;
    v17 = 16LL * g_SystemInfo.dwPageSize;
    if ( v17 > 0xFFFFFFFF )
    {
      VirtualFree(v16, 0, 0x8000u);
      return 0;
    }
    v18 = (struct _SLIST_ENTRY *)(unsigned int)v17;
    v19 = (struct _SLIST_ENTRY *)VirtualAlloc(v16, (unsigned int)v17, 0x1000u, 4u);
    v9 = v19;
    if ( !v19 )
      return 0;
    v19[1].Next = v18;
  }
  Next = v9[1].Next;
  *((_QWORD *)this + 11) = a2;
  *((_QWORD *)this + 12) = Next;
  *((_QWORD *)this + 10) = Next;
  v11 = *(unsigned int *)CReservedBlockManager::s_pInstance;
  v12 = 65534;
  *((_QWORD *)this + 8) = a3;
  *((_QWORD *)this + 13) = v11;
  *((_QWORD *)this + 9) = a4;
  if ( (unsigned int)v11 / a2 < 0xFFFE )
    v12 = (unsigned int)v11 / a2;
  *((_QWORD *)this + 4) = v12;
  if ( a2 <= *((_QWORD *)this + 12) )
  {
    v13 = a2 <= v11;
    goto LABEL_6;
  }
  v13 = a2 <= v11;
  if ( a2 >= v11 )
  {
LABEL_6:
    if ( v13 )
    {
LABEL_7:
      v14 = *((_QWORD *)this + 11);
      *((_QWORD *)this + 7) = (char *)v9 - a2;
      memset(v9, 0, v14);
      return 1;
    }
    return 0;
  }
  v20 = ~(16 * g_SystemInfo.dwPageSize - 1LL) & (16 * g_SystemInfo.dwPageSize - *((_QWORD *)this + 12) + a2 - 1);
  if ( VirtualAlloc((char *)v9 + *((_QWORD *)this + 12), v20, 0x1000u, 4u) )
  {
    *((_QWORD *)this + 12) += v20;
    *((_QWORD *)this + 10) = *((_QWORD *)this + 12);
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x383858630  mov     [rsp+arg_0], rbx
0x383858635  mov     [rsp+arg_8], rbp
0x38385863a  mov     [rsp+arg_10], rsi
0x38385863f  push    rdi
0x383858640  push    r14
0x383858642  push    r15
0x383858644  sub     rsp, 20h
0x383858648  mov     rbp, cs:?s_pInstance@CReservedBlockManager@@1PEAV1@EA; CReservedBlockManager * CReservedBlockManager::s_pInstance
0x38385864f  mov     rbx, rcx
0x383858652  mov     r14, r9
0x383858655  lea     rcx, [rbp+10h]; ListHead
0x383858659  mov     r15, r8
0x38385865c  mov     rsi, rdx
0x38385865f  call    cs:__imp_InterlockedPopEntrySList
0x383858665  mov     rdi, rax
0x383858668  test    rax, rax
0x38385866b  jz      loc_38389A2F8
0x383858671  mov     rax, [rdi+10h]
0x383858675  xor     edx, edx
0x383858677  mov     [rbx+58h], rsi
0x38385867b  mov     [rbx+60h], rax
0x38385867f  mov     [rbx+50h], rax
0x383858683  mov     rax, cs:?s_pInstance@CReservedBlockManager@@1PEAV1@EA; CReservedBlockManager * CReservedBlockManager::s_pInstance
0x38385868a  mov     r8d, [rax]
0x38385868d  mov     ecx, 0FFFEh
0x383858692  mov     [rbx+40h], r15
0x383858696  mov     eax, r8d
0x383858699  mov     [rbx+68h], r8
0x38385869d  mov     [rbx+48h], r14
0x3838586a1  div     rsi
0x3838586a4  cmp     rax, rcx
0x3838586a7  cmovb   rcx, rax
0x3838586ab  mov     [rbx+20h], rcx
0x3838586af  cmp     rsi, [rbx+60h]
0x3838586b3  ja      loc_3838F4D67
0x3838586b9  cmp     rsi, r8
0x3838586bc  ja      loc_3838F4D60
0x3838586c2  mov     r8, [rbx+58h]; Size
0x3838586c6  mov     rax, rdi
0x3838586c9  xor     edx, edx; Val
0x3838586cb  sub     rax, rsi
0x3838586ce  mov     rcx, rdi; void *
0x3838586d1  mov     [rbx+38h], rax
0x3838586d5  call    memset
0x3838586da  mov     eax, 1
0x3838586df  mov     rbx, [rsp+38h+arg_0]
0x3838586e4  mov     rbp, [rsp+38h+arg_8]
0x3838586e9  mov     rsi, [rsp+38h+arg_10]
0x3838586ee  add     rsp, 20h
0x3838586f2  pop     r15
0x3838586f4  pop     r14
0x3838586f6  pop     rdi
0x3838586f7  retn
0x38389a2f8  mov     edx, [rbp+0]; dwSize
0x38389a2fb  lea     r9d, [rax+4]; flProtect
0x38389a2ff  xor     ecx, ecx; lpAddress
0x38389a301  mov     r8d, 2000h; flAllocationType
0x38389a307  call    cs:__imp_VirtualAlloc
0x38389a30d  test    rax, rax
0x38389a310  jz      loc_3838F4D60
0x38389a316  mov     ecx, cs:?g_SystemInfo@@3U_SYSTEM_INFO@@A.dwPageSize; _SYSTEM_INFO g_SystemInfo ...
0x38389a31c  mov     edx, 0FFFFFFFFh
0x38389a321  shl     rcx, 4
0x38389a325  cmp     rcx, rdx
0x38389a328  ja      loc_3838F4D4F
0x38389a32e  mov     ebp, ecx
0x38389a330  mov     edx, ecx; dwSize
0x38389a332  mov     r9d, 4; flProtect
0x38389a338  mov     rcx, rax; lpAddress
0x38389a33b  mov     r8d, 1000h; flAllocationType
0x38389a341  call    cs:__imp_VirtualAlloc
0x38389a347  mov     rdi, rax
0x38389a34a  test    rax, rax
0x38389a34d  jz      loc_3838F4D60
0x38389a353  mov     [rax+10h], rbp
0x38389a357  jmp     loc_383858671
0x3838f4d4f  xor     edx, edx; dwSize
0x3838f4d51  mov     r8d, 8000h; dwFreeType
0x3838f4d57  mov     rcx, rax; lpAddress
0x3838f4d5a  call    cs:__imp_VirtualFree
0x3838f4d60  xor     eax, eax
0x3838f4d62  jmp     loc_3838586DF
0x3838f4d67  cmp     rsi, r8
0x3838f4d6a  jnb     loc_3838586BC
0x3838f4d70  mov     eax, cs:?g_SystemInfo@@3U_SYSTEM_INFO@@A.dwPageSize; _SYSTEM_INFO g_SystemInfo ...
0x3838f4d76  lea     rbp, [rsi-1]
0x3838f4d7a  mov     r9d, 4; flProtect
0x3838f4d80  shl     eax, 4
0x3838f4d83  mov     r8d, 1000h; flAllocationType
0x3838f4d89  mov     ecx, eax
0x3838f4d8b  sub     rax, [rbx+60h]
0x3838f4d8f  add     rbp, rax
0x3838f4d92  lea     rax, [rcx-1]
0x3838f4d96  mov     rcx, [rbx+60h]
0x3838f4d9a  not     rax
0x3838f4d9d  add     rcx, rdi; lpAddress
0x3838f4da0  and     rbp, rax
0x3838f4da3  mov     rdx, rbp; dwSize
0x3838f4da6  call    cs:__imp_VirtualAlloc
0x3838f4dac  test    rax, rax
0x3838f4daf  jz      short loc_3838F4D60
0x3838f4db1  add     [rbx+60h], rbp
0x3838f4db5  mov     rax, [rbx+60h]
0x3838f4db9  mov     [rbx+50h], rax
0x3838f4dbd  jmp     loc_3838586C2
```
