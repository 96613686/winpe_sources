# DumpUserData

- ea: `0x140014e98`
- end: `0x1400150ef`
- name: `DumpUserData`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140014ccc`

## callees

- `0x140009c78`
- `0x140014e98`
- `0x140015e84`
- `0x140016360`
- `0x1400164c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014f35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014f9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014fe0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014ff9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001509f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400150b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400150d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014f35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014f9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014fe0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014ff9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001509f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400150b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400150d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014ede`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014f06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014f27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014f90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014fae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014fd2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014feb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015091`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400150aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400150c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014ede`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014f06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014f27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014f90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014fae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014fd2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014feb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015091`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400150aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400150c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014eef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014f14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014fbf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014eef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014f14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014fbf`
- `wevtapi!EvtIntRenderResourceEventTemplate` at `0x140015045`
- `wevtapi!EvtIntRenderResourceEventTemplate` at `0x140015045`

## pseudocode

```c
int __fastcall DumpUserData(struct _iobuf **a1, unsigned int *a2)
{
  _UNKNOWN **v2; // rax
  __int64 v3; // r13
  void *v5; // rdi
  HANDLE ProcessHeap; // rax
  char *v7; // rsi
  HANDLE v8; // rax
  _QWORD *v9; // rbp
  HANDLE v10; // rax
  unsigned int v11; // r14d
  __int64 v12; // r12
  unsigned __int16 *v13; // rbx
  __int64 v14; // rax
  HANDLE v15; // rax
  SIZE_T v16; // rbx
  HANDLE v17; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  char *v20; // rcx
  HANDLE v21; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h] BYREF
  unsigned int v27; // [rsp+88h] [rbp+10h] BYREF

  v2 = &retaddr;
  v3 = a2[26];
  v27 = 0;
  if ( (_DWORD)v3 )
  {
    v5 = 0;
    ProcessHeap = GetProcessHeap();
    v7 = (char *)HeapAlloc(ProcessHeap, 8u, 20 * v3);
    if ( !v7 )
      RaiseAllocationFailure();
    v8 = GetProcessHeap();
    v9 = HeapAlloc(v8, 8u, 16LL * (unsigned int)v3);
    if ( !v9 )
    {
      if ( v7 )
      {
        v10 = GetProcessHeap();
        HeapFree(v10, 0, v7);
      }
      RaiseAllocationFailure();
    }
    v11 = 0;
    v12 = 0;
    do
    {
      ++v11;
      v13 = (unsigned __int16 *)&v7[20 * v12];
      StringCchPrintfW(v13, 0xAu, L"%%%d", v11);
      v14 = v12++;
      v14 *= 2;
      v9[v14] = v13;
      LODWORD(v9[v14 + 1]) = 1;
      HIDWORD(v9[v14 + 1]) = 1;
    }
    while ( v11 < (unsigned int)v3 );
    do
    {
      if ( v5 )
      {
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v5);
      }
      v16 = 2LL * v27;
      v17 = GetProcessHeap();
      v5 = HeapAlloc(v17, 8u, v16);
      if ( !v5 )
      {
        if ( v7 )
        {
          v18 = GetProcessHeap();
          HeapFree(v18, 0, v7);
        }
        if ( v9 )
        {
          v19 = GetProcessHeap();
          HeapFree(v19, 0, v9);
        }
        RaiseAllocationFailure();
      }
      if ( a2[21] )
        v20 = (char *)a2 + a2[21];
      else
        v20 = 0;
    }
    while ( (unsigned int)EvtIntRenderResourceEventTemplate(v20, a2[22], v9, (unsigned int)v3, 0, v27, v5, &v27) == 122 );
    TracerptFPutws((wchar_t *)L"\t\t\t\t<UserData>\r\n", *a1);
    TracerptFWPrintf(*a1, (wchar_t *)L"\t\t\t\t\t%ws\r\n", v5);
    LODWORD(v2) = TracerptFPutws((wchar_t *)L"\t\t\t\t</UserData>\r\n", *a1);
    if ( v7 )
    {
      v21 = GetProcessHeap();
      LODWORD(v2) = HeapFree(v21, 0, v7);
    }
    if ( v5 )
    {
      v22 = GetProcessHeap();
      LODWORD(v2) = HeapFree(v22, 0, v5);
    }
    if ( v9 )
    {
      v23 = GetProcessHeap();
      LODWORD(v2) = HeapFree(v23, 0, v9);
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x140014e98  mov     rax, rsp
0x140014e9b  mov     [rax+18h], rbx
0x140014e9f  mov     [rax+8], rcx
0x140014ea3  push    rbp
0x140014ea4  push    rsi
0x140014ea5  push    rdi
0x140014ea6  push    r12
0x140014ea8  push    r13
0x140014eaa  push    r14
0x140014eac  push    r15
0x140014eae  sub     rsp, 40h
0x140014eb2  mov     r13d, [rdx+68h]
0x140014eb6  mov     r15, rdx
0x140014eb9  mov     dword ptr [rax+10h], 0
0x140014ec0  cmp     r13d, 1
0x140014ec4  jb      loc_1400150D7
0x140014eca  lea     rbx, ds:0[r13*4]
0x140014ed2  xor     edi, edi
0x140014ed4  add     rbx, r13
0x140014ed7  mov     r14d, r13d
0x140014eda  shl     rbx, 2
0x140014ede  call    cs:__imp_GetProcessHeap
0x140014ee4  mov     r8, rbx; dwBytes
0x140014ee7  lea     ebx, [rdi+8]
0x140014eea  mov     edx, ebx; dwFlags
0x140014eec  mov     rcx, rax; hHeap
0x140014eef  call    cs:__imp_HeapAlloc
0x140014ef5  mov     rsi, rax
0x140014ef8  test    rax, rax
0x140014efb  jnz     short loc_140014F02
0x140014efd  call    RaiseAllocationFailure
0x140014f02  shl     r14, 4
0x140014f06  call    cs:__imp_GetProcessHeap
0x140014f0c  mov     r8, r14; dwBytes
0x140014f0f  mov     edx, ebx; dwFlags
0x140014f11  mov     rcx, rax; hHeap
0x140014f14  call    cs:__imp_HeapAlloc
0x140014f1a  mov     rbp, rax
0x140014f1d  test    rax, rax
0x140014f20  jnz     short loc_140014F40
0x140014f22  test    rsi, rsi
0x140014f25  jz      short loc_140014F3B
0x140014f27  call    cs:__imp_GetProcessHeap
0x140014f2d  mov     r8, rsi; lpMem
0x140014f30  xor     edx, edx; dwFlags
0x140014f32  mov     rcx, rax; hHeap
0x140014f35  call    cs:__imp_HeapFree
0x140014f3b  call    RaiseAllocationFailure
0x140014f40  xor     r14d, r14d
0x140014f43  xor     r12d, r12d
0x140014f46  lea     rax, [r12+r12*4]
0x140014f4a  inc     r14d
0x140014f4d  lea     rbx, [rsi+rax*4]
0x140014f51  mov     r9d, r14d
0x140014f54  mov     rcx, rbx; unsigned __int16 *
0x140014f57  lea     r8, aD_0; "%%%d"
0x140014f5e  mov     edx, 0Ah; unsigned __int64
0x140014f63  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014f68  mov     rax, r12
0x140014f6b  inc     r12
0x140014f6e  add     rax, rax
0x140014f71  mov     [rbp+rax*8+0], rbx
0x140014f76  mov     dword ptr [rbp+rax*8+8], 1
0x140014f7e  mov     dword ptr [rbp+rax*8+0Ch], 1
0x140014f86  cmp     r14d, r13d
0x140014f89  jb      short loc_140014F46
0x140014f8b  test    rdi, rdi
0x140014f8e  jz      short loc_140014FA4
0x140014f90  call    cs:__imp_GetProcessHeap
0x140014f96  mov     r8, rdi; lpMem
0x140014f99  xor     edx, edx; dwFlags
0x140014f9b  mov     rcx, rax; hHeap
0x140014f9e  call    cs:__imp_HeapFree
0x140014fa4  mov     ebx, [rsp+78h+arg_8]
0x140014fab  add     rbx, rbx
0x140014fae  call    cs:__imp_GetProcessHeap
0x140014fb4  mov     r8, rbx; dwBytes
0x140014fb7  mov     edx, 8; dwFlags
0x140014fbc  mov     rcx, rax; hHeap
0x140014fbf  call    cs:__imp_HeapAlloc
0x140014fc5  mov     rdi, rax
0x140014fc8  test    rax, rax
0x140014fcb  jnz     short loc_140015004
0x140014fcd  test    rsi, rsi
0x140014fd0  jz      short loc_140014FE6
0x140014fd2  call    cs:__imp_GetProcessHeap
0x140014fd8  mov     r8, rsi; lpMem
0x140014fdb  xor     edx, edx; dwFlags
0x140014fdd  mov     rcx, rax; hHeap
0x140014fe0  call    cs:__imp_HeapFree
0x140014fe6  test    rbp, rbp
0x140014fe9  jz      short loc_140014FFF
0x140014feb  call    cs:__imp_GetProcessHeap
0x140014ff1  mov     r8, rbp; lpMem
0x140014ff4  xor     edx, edx; dwFlags
0x140014ff6  mov     rcx, rax; hHeap
0x140014ff9  call    cs:__imp_HeapFree
0x140014fff  call    RaiseAllocationFailure
0x140015004  cmp     dword ptr [r15+54h], 0
0x140015009  jnz     short loc_14001500F
0x14001500b  xor     ecx, ecx
0x14001500d  jmp     short loc_140015016
0x14001500f  mov     ecx, [r15+54h]
0x140015013  add     rcx, r15
0x140015016  mov     edx, [r15+58h]
0x14001501a  lea     rax, [rsp+78h+arg_8]
0x140015022  mov     [rsp+78h+var_40], rax
0x140015027  mov     r9d, r13d
0x14001502a  mov     eax, [rsp+78h+arg_8]
0x140015031  mov     r8, rbp
0x140015034  mov     [rsp+78h+var_48], rdi
0x140015039  mov     [rsp+78h+var_50], eax
0x14001503d  mov     [rsp+78h+var_58], 0
0x140015045  call    cs:__imp_EvtIntRenderResourceEventTemplate
0x14001504b  cmp     eax, 7Ah ; 'z'
0x14001504e  jz      loc_140014F8B
0x140015054  mov     rbx, [rsp+78h+arg_0]
0x14001505c  lea     rcx, aUserdata; "\t\t\t\t<UserData>\r\n"
0x140015063  mov     rdx, [rbx]; struct _iobuf *
0x140015066  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001506b  mov     rcx, [rbx]; struct _iobuf *
0x14001506e  lea     rdx, aWs_9; "\t\t\t\t\t%ws\r\n"
0x140015075  mov     r8, rdi
0x140015078  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001507d  mov     rdx, [rbx]; struct _iobuf *
0x140015080  lea     rcx, aUserdata_0; "\t\t\t\t</UserData>\r\n"
0x140015087  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001508c  test    rsi, rsi
0x14001508f  jz      short loc_1400150A5
0x140015091  call    cs:__imp_GetProcessHeap
0x140015097  mov     r8, rsi; lpMem
0x14001509a  xor     edx, edx; dwFlags
0x14001509c  mov     rcx, rax; hHeap
0x14001509f  call    cs:__imp_HeapFree
0x1400150a5  test    rdi, rdi
0x1400150a8  jz      short loc_1400150BE
0x1400150aa  call    cs:__imp_GetProcessHeap
0x1400150b0  mov     r8, rdi; lpMem
0x1400150b3  xor     edx, edx; dwFlags
0x1400150b5  mov     rcx, rax; hHeap
0x1400150b8  call    cs:__imp_HeapFree
0x1400150be  test    rbp, rbp
0x1400150c1  jz      short loc_1400150D7
0x1400150c3  call    cs:__imp_GetProcessHeap
0x1400150c9  mov     r8, rbp; lpMem
0x1400150cc  xor     edx, edx; dwFlags
0x1400150ce  mov     rcx, rax; hHeap
0x1400150d1  call    cs:__imp_HeapFree
0x1400150d7  mov     rbx, [rsp+78h+arg_10]
0x1400150df  add     rsp, 40h
0x1400150e3  pop     r15
0x1400150e5  pop     r14
0x1400150e7  pop     r13
0x1400150e9  pop     r12
0x1400150eb  pop     rdi
0x1400150ec  pop     rsi
0x1400150ed  pop     rbp
0x1400150ee  retn
```
