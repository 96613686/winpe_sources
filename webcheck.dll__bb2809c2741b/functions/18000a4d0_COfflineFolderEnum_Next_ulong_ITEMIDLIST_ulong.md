# COfflineFolderEnum::Next(ulong,_ITEMIDLIST * *,ulong *)

- ea: `0x18000a4d0`
- end: `0x18000a6cc`
- name: `?Next@COfflineFolderEnum@@UEAAJKPEAPEFAU_ITEMIDLIST@@PEAK@Z`
- size: `508`
- prototype: `__int64 __fastcall(COfflineFolderEnum *__hidden this, unsigned int, struct _ITEMIDLIST **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000a4d0`
- `0x18000cc84`
- `0x18000dd40`
- `0x18000e150`
- `0x18001c384`
- `0x180029236`
- `0x18002924e`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000a60b`
- `ole32!CoTaskMemAlloc` at `0x18000a60b`
- `ole32!CoTaskMemFree` at `0x18000a672`
- `ole32!CoTaskMemFree` at `0x18000a672`

## pseudocode

```c
__int64 __fastcall COfflineFolderEnum::Next(
        COfflineFolderEnum *this,
        unsigned int a2,
        struct _ITEMIDLIST **a3,
        unsigned int *a4)
{
  struct _ITEMIDLIST **v5; // r15
  int OOEntryInfo; // edi
  __int64 v9; // rbx
  unsigned int v10; // r9d
  struct _ITEMIDLIST *v11; // rax
  struct _ITEMIDLIST *v12; // r13
  __int64 i; // rsi
  size_t Size[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[116]; // [rsp+40h] [rbp-C0h] BYREF
  IID rclsid; // [rsp+B4h] [rbp-4Ch] BYREF
  char Buf1[404]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v20[2482]; // [rsp+26Ch] [rbp+16Ch] BYREF

  v5 = a3;
  if ( !a2 || a2 > 1 && !a4 || !a3 )
    return 2147942487LL;
  OOEntryInfo = 0;
  memset_0(v17, 0, 0x1590u);
  v9 = 0;
  do
  {
    if ( *((_DWORD *)this + 5) >= *((_DWORD *)this + 4) )
      goto LABEL_20;
    if ( (unsigned int)v9 >= a2 )
      break;
    v5[v9] = 0;
    OOEntryInfo = LoadOOEntryInfo((struct OOEBuf *)v17);
    if ( OOEntryInfo >= 0 )
    {
      if ( !memcmp_0(Buf1, &CLSID_WebCrawlerAgent, 0x10u) )
      {
        *(_OWORD *)Size = 0;
        if ( (unsigned int)ReadCookieFromInetDB(v20, (LPIID)Size) )
          WriteCookieToInetDB(v20, &rclsid, 0, v10);
      }
      Size[0] = 226;
      v11 = (struct _ITEMIDLIST *)CoTaskMemAlloc(0xE2u);
      v12 = v11;
      if ( v11 )
      {
        memset_0(v11, 0, Size[0]);
        v12->mkid.cb = 224;
        *(_WORD *)v12->mkid.abID = 29701;
        CopyToMyPooe(v17, v12[2].mkid.abID);
        v5 = a3;
        a3[v9] = v12;
      }
      else
      {
        v5 = a3;
        OOEntryInfo = -2147024882;
      }
    }
    ++*((_DWORD *)this + 5);
    v9 = (unsigned int)(v9 + 1);
  }
  while ( !OOEntryInfo );
  if ( OOEntryInfo >= 0 )
  {
LABEL_20:
    OOEntryInfo = a2 != v9;
    goto LABEL_21;
  }
  for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
    CoTaskMemFree(v5[i]);
LABEL_21:
  if ( a4 )
  {
    if ( OOEntryInfo < 0 )
      LODWORD(v9) = 0;
    *a4 = v9;
  }
  return (unsigned int)OOEntryInfo;
}

```

## disassembly

```asm
0x18000a4d0  mov     [rsp-8+arg_8], rbx
0x18000a4d5  push    rbp
0x18000a4d6  push    rsi
0x18000a4d7  push    rdi
0x18000a4d8  push    r12
0x18000a4da  push    r13
0x18000a4dc  push    r14
0x18000a4de  push    r15
0x18000a4e0  lea     rbp, [rsp-14E0h]
0x18000a4e8  mov     eax, 15E0h
0x18000a4ed  call    _alloca_probe
0x18000a4f2  sub     rsp, rax
0x18000a4f5  mov     rax, cs:__security_cookie
0x18000a4fc  xor     rax, rsp
0x18000a4ff  mov     [rbp+1510h+var_40], rax
0x18000a506  mov     [rsp+1610h+var_15E8], r8
0x18000a50b  mov     r12, r9
0x18000a50e  mov     [rsp+1610h+var_15F0], 0
0x18000a516  mov     r15, r8
0x18000a519  mov     r14d, edx
0x18000a51c  mov     rsi, rcx
0x18000a51f  test    edx, edx
0x18000a521  jz      loc_18000A69D
0x18000a527  cmp     edx, 1
0x18000a52a  jbe     short loc_18000A535
0x18000a52c  test    r9, r9
0x18000a52f  jz      loc_18000A69D
0x18000a535  test    r8, r8
0x18000a538  jz      loc_18000A69D
0x18000a53e  xor     edx, edx; Val
0x18000a540  lea     rcx, [rsp+1610h+var_15D0]; void *
0x18000a545  mov     r8d, 1590h; Size
0x18000a54b  xor     edi, edi
0x18000a54d  call    memset_0
0x18000a552  xor     ebx, ebx
0x18000a554  mov     eax, [rsi+10h]
0x18000a557  cmp     [rsi+14h], eax
0x18000a55a  jnb     loc_18000A680
0x18000a560  cmp     ebx, r14d
0x18000a563  jnb     loc_18000A664
0x18000a569  mov     qword ptr [r15+rbx*8], 0
0x18000a571  lea     r8, [rsp+1610h+var_15F0]
0x18000a576  mov     edx, [rsi+14h]
0x18000a579  lea     rcx, [rsp+1610h+var_15D0]; struct OOEBuf *
0x18000a57e  shl     rdx, 4
0x18000a582  add     rdx, [rsi+18h]
0x18000a586  call    LoadOOEntryInfo
0x18000a58b  mov     edi, eax
0x18000a58d  test    eax, eax
0x18000a58f  js      loc_18000A657
0x18000a595  mov     r8d, 10h; Size
0x18000a59b  lea     rdx, CLSID_WebCrawlerAgent; Buf2
0x18000a5a2  lea     rcx, [rbp+1510h+Buf1]; Buf1
0x18000a5a6  call    memcmp_0
0x18000a5ab  test    eax, eax
0x18000a5ad  jnz     short loc_18000A5DF
0x18000a5af  xorps   xmm0, xmm0
0x18000a5b2  lea     rdx, [rsp+1610h+Size]; lpiid
0x18000a5b7  lea     rcx, [rbp+1510h+var_13A4]; unsigned __int16 *
0x18000a5be  movups  xmmword ptr [rsp+1610h+Size], xmm0
0x18000a5c3  call    ?ReadCookieFromInetDB@@YAJPEBGPEAU_GUID@@@Z; ReadCookieFromInetDB(ushort const *,_GUID *)
0x18000a5c8  test    eax, eax
0x18000a5ca  jz      short loc_18000A5DF
0x18000a5cc  xor     r8d, r8d; int
0x18000a5cf  lea     rdx, [rbp+1510h+rclsid]; rclsid
0x18000a5d3  lea     rcx, [rbp+1510h+var_13A4]; unsigned __int16 *
0x18000a5da  call    ?WriteCookieToInetDB@@YAJPEBGPEBU_GUID@@H@Z; WriteCookieToInetDB(ushort const *,_GUID const *,int)
0x18000a5df  mov     eax, [rsp+1610h+var_15F0]
0x18000a5e3  cmp     eax, 0FFFFh
0x18000a5e8  ja      short loc_18000A652
0x18000a5ea  mov     r15d, 0E0h
0x18000a5f0  add     r15d, eax
0x18000a5f3  cmp     r15w, ax
0x18000a5f7  jb      short loc_18000A64D
0x18000a5f9  movzx   eax, r15w
0x18000a5fd  lea     rcx, [rax+2]; cb
0x18000a601  mov     [rsp+1610h+Size], rcx
0x18000a606  cmp     rcx, rax
0x18000a609  jb      short loc_18000A64D
0x18000a60b  call    cs:__imp_CoTaskMemAlloc
0x18000a611  mov     r13, rax
0x18000a614  test    rax, rax
0x18000a617  jz      short loc_18000A64D
0x18000a619  mov     r8, [rsp+1610h+Size]; Size
0x18000a61e  xor     edx, edx; Val
0x18000a620  mov     rcx, rax; void *
0x18000a623  call    memset_0
0x18000a628  lea     rdx, [r13+8]
0x18000a62c  mov     [r13+0], r15w
0x18000a631  lea     rcx, [rsp+1610h+var_15D0]
0x18000a636  mov     word ptr [r13+2], 7405h
0x18000a63d  call    CopyToMyPooe
0x18000a642  mov     r15, [rsp+1610h+var_15E8]
0x18000a647  mov     [r15+rbx*8], r13
0x18000a64b  jmp     short loc_18000A657
0x18000a64d  mov     r15, [rsp+1610h+var_15E8]
0x18000a652  mov     edi, 8007000Eh
0x18000a657  inc     dword ptr [rsi+14h]
0x18000a65a  inc     ebx
0x18000a65c  test    edi, edi
0x18000a65e  jz      loc_18000A554
0x18000a664  test    edi, edi
0x18000a666  jns     short loc_18000A680
0x18000a668  xor     esi, esi
0x18000a66a  test    ebx, ebx
0x18000a66c  jz      short loc_18000A689
0x18000a66e  mov     rcx, [r15+rsi*8]; pv
0x18000a672  call    cs:__imp_CoTaskMemFree
0x18000a678  inc     esi
0x18000a67a  cmp     esi, ebx
0x18000a67c  jb      short loc_18000A66E
0x18000a67e  jmp     short loc_18000A689
0x18000a680  xor     edi, edi
0x18000a682  cmp     r14d, ebx
0x18000a685  setnz   dil
0x18000a689  test    r12, r12
0x18000a68c  jz      short loc_18000A699
0x18000a68e  xor     eax, eax
0x18000a690  test    edi, edi
0x18000a692  cmovs   ebx, eax
0x18000a695  mov     [r12], ebx
0x18000a699  mov     eax, edi
0x18000a69b  jmp     short loc_18000A6A2
0x18000a69d  mov     eax, 80070057h
0x18000a6a2  mov     rcx, [rbp+1510h+var_40]
0x18000a6a9  xor     rcx, rsp; StackCookie
0x18000a6ac  call    __security_check_cookie
0x18000a6b1  mov     rbx, [rsp+1610h+arg_8]
0x18000a6b9  add     rsp, 15E0h
0x18000a6c0  pop     r15
0x18000a6c2  pop     r14
0x18000a6c4  pop     r13
0x18000a6c6  pop     r12
0x18000a6c8  pop     rdi
0x18000a6c9  pop     rsi
0x18000a6ca  pop     rbp
0x18000a6cb  retn
```
