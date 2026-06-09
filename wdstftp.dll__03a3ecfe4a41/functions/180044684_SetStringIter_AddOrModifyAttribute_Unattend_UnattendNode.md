# SetStringIter::AddOrModifyAttribute(Unattend &,UnattendNode)

- ea: `0x180044684`
- end: `0x1800449e1`
- name: `?AddOrModifyAttribute@SetStringIter@@QEAAJAEAVUnattend@@VUnattendNode@@@Z`
- size: `861`
- prototype: `int __high(struct Unattend *, struct UnattendNode)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800449f0`

## callees

- `0x180041c8c`
- `0x180041d98`
- `0x180043764`
- `0x180043e58`
- `0x180044684`
- `0x18004537c`
- `0x180045448`
- `0x180048cd4`
- `0x180048d60`
- `0x1800490c8`
- `0x1800607b0`
- `0x180060e70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180044797`
- `KERNEL32!HeapFree` at `0x1800447c8`
- `KERNEL32!HeapFree` at `0x1800449ac`
- `KERNEL32!HeapFree` at `0x180044797`
- `KERNEL32!HeapFree` at `0x1800447c8`
- `KERNEL32!HeapFree` at `0x1800449ac`
- `KERNEL32!GetProcessHeap` at `0x180044783`
- `KERNEL32!GetProcessHeap` at `0x1800447b4`
- `KERNEL32!GetProcessHeap` at `0x180044998`
- `KERNEL32!GetProcessHeap` at `0x180044783`
- `KERNEL32!GetProcessHeap` at `0x1800447b4`
- `KERNEL32!GetProcessHeap` at `0x180044998`
- `KERNEL32!CompareStringW` at `0x180044749`
- `KERNEL32!CompareStringW` at `0x180044749`
- `ntdll!RtlNtStatusToDosError` at `0x18004494d`
- `ntdll!RtlNtStatusToDosError` at `0x180044979`
- `ntdll!RtlNtStatusToDosError` at `0x18004494d`
- `ntdll!RtlNtStatusToDosError` at `0x180044979`

## pseudocode

```c
__int64 __fastcall SetStringIter::AddOrModifyAttribute(__int64 a1, Unattend *a2, const struct UnattendNode *a3)
{
  void *v3; // rsi
  unsigned __int64 v4; // r15
  const struct UnattendNode *v5; // r12
  _QWORD *v7; // rdi
  void *v8; // r14
  signed int AttributeInfo; // ebx
  char v10; // di
  WCHAR *v11; // r12
  unsigned __int16 *v12; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v14; // rax
  bool v15; // zf
  __int64 v16; // rcx
  NTSTATUS CookieForExistingAttribute; // eax
  const unsigned __int16 *v18; // rcx
  _QWORD *v19; // rsi
  NTSTATUS updated; // eax
  signed int v21; // eax
  signed int v22; // eax
  HANDLE v23; // rax
  LPVOID lpMem; // [rsp+38h] [rbp-51h] BYREF
  _QWORD *v26; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v27; // [rsp+48h] [rbp-41h] BYREF
  __int128 v28; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int64 v29; // [rsp+60h] [rbp-29h] BYREF
  PCNZWCH lpString2; // [rsp+68h] [rbp-21h] BYREF
  const struct UnattendNode *v31; // [rsp+70h] [rbp-19h]
  __int128 v32; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v33[24]; // [rsp+90h] [rbp+7h] BYREF

  v3 = *(void **)(a1 + 16);
  v4 = 0;
  v31 = a3;
  v5 = a3;
  v26 = (_QWORD *)a1;
  lpMem = v3;
  v7 = (_QWORD *)a1;
  if ( v3 )
  {
    v8 = lpMem;
    AttributeInfo = Unattend::CountAttributes(a2, a3, &v29);
    if ( AttributeInfo >= 0 )
    {
      v10 = 0;
      do
      {
        if ( v4 >= v29 )
          break;
        AttributeInfo = Unattend::GetAttributeInfo(
                          a2,
                          v5,
                          v4,
                          (unsigned __int16 **)&lpString2,
                          &v27,
                          (struct UnattendNode *)&v32);
        if ( AttributeInfo >= 0 )
        {
          v11 = (WCHAR *)lpString2;
          if ( CompareStringW(0x409u, 1u, (PCNZWCH)v3, -1, lpString2, -1) == 2 )
          {
            v8 = v27;
            v12 = 0;
            v4 = v29;
            AttributeInfo = 0;
            v27 = 0;
            v10 = 1;
            v28 = v32;
          }
          else
          {
            v12 = v27;
          }
          if ( v11 )
          {
            ProcessHeap = GetProcessHeap();
            if ( HeapFree(ProcessHeap, 0, v11) )
              v11 = 0;
            lpString2 = v11;
          }
          if ( v12 )
          {
            v14 = GetProcessHeap();
            if ( HeapFree(v14, 0, v12) )
              v12 = 0;
            v27 = v12;
          }
          v3 = lpMem;
          v5 = v31;
        }
        ++v4;
      }
      while ( AttributeInfo >= 0 );
      v15 = v10 == 0;
      v7 = v26;
      if ( v15 && AttributeInfo >= 0 )
      {
        AttributeInfo = 1;
        v8 = 0;
      }
    }
  }
  else
  {
    v8 = 0;
    AttributeInfo = -2147024809;
  }
  if ( AttributeInfo == 1 )
  {
    if ( v7[9] )
    {
      v32 = *(_OWORD *)v5;
      AttributeInfo = SetStringIter::GetModifyContext(v7, a2, &v32, &v26);
      if ( AttributeInfo >= 0 )
        return (unsigned int)SetStringIter::AddDataAttribute(v7, v26, v7[2], v7[9]);
    }
    else
    {
      return 1;
    }
    return (unsigned int)AttributeInfo;
  }
  if ( AttributeInfo < 0 )
    return (unsigned int)AttributeInfo;
  if ( (*(int (__fastcall **)(_QWORD, __int128 *, __int128 *))(**(_QWORD **)a2 + 56LL))(*(_QWORD *)a2, &v28, &v32) >= 0 )
  {
    v16 = v7[8];
    v28 = v32;
    CookieForExistingAttribute = RtlMicrodomUpdateGetCookieForExistingAttribute(v16, &v28, &lpMem);
    if ( CookieForExistingAttribute < 0 )
    {
      v22 = RtlNtStatusToDosError(CookieForExistingAttribute);
      AttributeInfo = (unsigned __int16)v22 | 0x80070000;
      if ( v22 <= 0 )
        AttributeInfo = v22;
      goto LABEL_46;
    }
    v18 = (const unsigned __int16 *)v7[9];
    v19 = 0;
    if ( v18 )
    {
      AttributeInfo = UnicodeToUtf8(v18, (struct _LUTF8_STRING *)v33);
      if ( AttributeInfo < 0 )
        goto LABEL_46;
      v19 = v33;
    }
    if ( v19 )
    {
      updated = RtlMicrodomUpdateSetNodeTextContent(v7[8], (__int64)lpMem, v19);
      if ( updated >= 0 )
      {
        AttributeInfo = 0;
LABEL_42:
        if ( v19 )
          FreeUtf8((struct _LUTF8_STRING *)v33);
        goto LABEL_46;
      }
LABEL_40:
      v21 = RtlNtStatusToDosError(updated);
      AttributeInfo = (unsigned __int16)v21 | 0x80070000;
      if ( v21 <= 0 )
        AttributeInfo = v21;
      goto LABEL_42;
    }
    v28 = *(_OWORD *)v5;
    AttributeInfo = SetStringIter::GetModifyContext(v7, a2, &v28, &v26);
    if ( AttributeInfo >= 0 )
    {
      updated = RtlMicrodomUpdateRemoveChild(v7[8], (__int64)v26, (struct CChildNode *)lpMem);
      if ( updated < 0 )
        goto LABEL_40;
      AttributeInfo = 0;
    }
  }
LABEL_46:
  if ( v8 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v8);
  }
  return (unsigned int)AttributeInfo;
}

```

## disassembly

```asm
0x180044684  mov     [rsp-8+arg_18], rbx
0x180044689  push    rbp
0x18004468a  push    rsi
0x18004468b  push    rdi
0x18004468c  push    r12
0x18004468e  push    r13
0x180044690  push    r14
0x180044692  push    r15
0x180044694  lea     rbp, [rsp-27h]
0x180044699  sub     rsp, 0B0h
0x1800446a0  mov     rax, cs:__security_cookie
0x1800446a7  xor     rax, rsp
0x1800446aa  mov     [rbp+57h+var_38], rax
0x1800446ae  mov     rsi, [rcx+10h]
0x1800446b2  xor     r15d, r15d
0x1800446b5  mov     [rbp+57h+var_70], r8
0x1800446b9  mov     r12, r8
0x1800446bc  mov     [rbp+57h+var_A0], rcx
0x1800446c0  mov     r13, rdx
0x1800446c3  mov     [rbp+57h+lpMem], rsi
0x1800446c7  mov     rdi, rcx
0x1800446ca  test    rsi, rsi
0x1800446cd  jz      loc_18004480C
0x1800446d3  lea     r8, [rbp+57h+var_80]; unsigned __int64 *
0x1800446d7  mov     rdx, r12; struct UnattendNode *
0x1800446da  mov     rcx, r13; this
0x1800446dd  call    ?CountAttributes@Unattend@@QEAAJAEBVUnattendNode@@AEA_K@Z; Unattend::CountAttributes(UnattendNode const &,unsigned __int64 &)
0x1800446e2  mov     r14, [rbp+57h+lpMem]
0x1800446e6  mov     ebx, eax
0x1800446e8  test    eax, eax
0x1800446ea  js      loc_180044815
0x1800446f0  mov     dil, r15b
0x1800446f3  cmp     r15, [rbp+57h+var_80]
0x1800446f7  jnb     loc_1800447F3
0x1800446fd  lea     rax, [rbp+57h+var_60]
0x180044701  mov     r8, r15; unsigned __int64
0x180044704  mov     qword ptr [rsp+0E0h+cchCount2], rax; struct UnattendNode *
0x180044709  lea     r9, [rbp+57h+var_78]; unsigned __int16 **
0x18004470d  lea     rax, [rbp+57h+var_98]
0x180044711  mov     rdx, r12; struct UnattendNode *
0x180044714  mov     rcx, r13; this
0x180044717  mov     [rsp+0E0h+lpString2], rax; unsigned __int16 **
0x18004471c  call    ?GetAttributeInfo@Unattend@@QEAAJAEBVUnattendNode@@_KPEAPEAG2PEAV2@@Z; Unattend::GetAttributeInfo(UnattendNode const &,unsigned __int64,ushort * *,ushort * *,UnattendNode *)
0x180044721  mov     ebx, eax
0x180044723  test    eax, eax
0x180044725  js      loc_1800447E8
0x18004472b  mov     r12, [rbp+57h+var_78]
0x18004472f  or      eax, 0FFFFFFFFh
0x180044732  mov     [rsp+0E0h+cchCount2], eax; cchCount2
0x180044736  mov     r9d, eax; cchCount1
0x180044739  mov     r8, rsi; lpString1
0x18004473c  mov     [rsp+0E0h+lpString2], r12; lpString2
0x180044741  mov     ecx, 409h; Locale
0x180044746  lea     edx, [rax+2]; dwCmpFlags
0x180044749  call    cs:__imp_CompareStringW
0x180044750  nop     dword ptr [rax+rax+00h]
0x180044755  cmp     eax, 2
0x180044758  jnz     short loc_18004477A
0x18004475a  movaps  xmm0, [rbp+57h+var_60]
0x18004475e  xor     ecx, ecx
0x180044760  mov     r14, [rbp+57h+var_98]
0x180044764  mov     esi, ecx
0x180044766  mov     r15, [rbp+57h+var_80]
0x18004476a  mov     ebx, ecx
0x18004476c  mov     [rbp+57h+var_98], rcx
0x180044770  mov     dil, 1
0x180044773  movdqa  [rbp+57h+var_90], xmm0
0x180044778  jmp     short loc_18004477E
0x18004477a  mov     rsi, [rbp+57h+var_98]
0x18004477e  test    r12, r12
0x180044781  jz      short loc_1800447AF
0x180044783  call    cs:__imp_GetProcessHeap
0x18004478a  nop     dword ptr [rax+rax+00h]
0x18004478f  mov     r8, r12; lpMem
0x180044792  xor     edx, edx; dwFlags
0x180044794  mov     rcx, rax; hHeap
0x180044797  call    cs:__imp_HeapFree
0x18004479e  nop     dword ptr [rax+rax+00h]
0x1800447a3  xor     ecx, ecx
0x1800447a5  test    eax, eax
0x1800447a7  cmovnz  r12, rcx
0x1800447ab  mov     [rbp+57h+var_78], r12
0x1800447af  test    rsi, rsi
0x1800447b2  jz      short loc_1800447E0
0x1800447b4  call    cs:__imp_GetProcessHeap
0x1800447bb  nop     dword ptr [rax+rax+00h]
0x1800447c0  mov     r8, rsi; lpMem
0x1800447c3  xor     edx, edx; dwFlags
0x1800447c5  mov     rcx, rax; hHeap
0x1800447c8  call    cs:__imp_HeapFree
0x1800447cf  nop     dword ptr [rax+rax+00h]
0x1800447d4  xor     ecx, ecx
0x1800447d6  test    eax, eax
0x1800447d8  cmovnz  rsi, rcx
0x1800447dc  mov     [rbp+57h+var_98], rsi
0x1800447e0  mov     rsi, [rbp+57h+lpMem]
0x1800447e4  mov     r12, [rbp+57h+var_70]
0x1800447e8  inc     r15
0x1800447eb  test    ebx, ebx
0x1800447ed  jns     loc_1800446F3
0x1800447f3  xor     r15d, r15d
0x1800447f6  test    dil, dil
0x1800447f9  mov     rdi, [rbp+57h+var_A0]
0x1800447fd  jnz     short loc_180044815
0x1800447ff  test    ebx, ebx
0x180044801  js      short loc_180044815
0x180044803  lea     ebx, [r15+1]
0x180044807  mov     r14d, r15d
0x18004480a  jmp     short loc_180044815
0x18004480c  mov     r14, [rbp+57h+lpMem]
0x180044810  mov     ebx, 80070057h
0x180044815  cmp     ebx, 1
0x180044818  jnz     short loc_18004486C
0x18004481a  cmp     [rdi+48h], r15
0x18004481e  jz      short loc_180044862
0x180044820  movaps  xmm0, xmmword ptr [r12]
0x180044825  lea     r9, [rbp+57h+var_A0]
0x180044829  lea     r8, [rbp+57h+var_60]
0x18004482d  movdqa  [rbp+57h+var_60], xmm0
0x180044832  mov     rdx, r13
0x180044835  mov     rcx, rdi
0x180044838  call    ?GetModifyContext@SetStringIter@@QEAAJAEAVUnattend@@VUnattendNode@@AEAUModifyContext@1@@Z; SetStringIter::GetModifyContext(Unattend &,UnattendNode,SetStringIter::ModifyContext &)
0x18004483d  mov     ebx, eax
0x18004483f  test    eax, eax
0x180044841  js      loc_1800449B8
0x180044847  mov     r9, [rdi+48h]
0x18004484b  mov     rcx, rdi
0x18004484e  mov     r8, [rdi+10h]
0x180044852  mov     rdx, [rbp+57h+var_A0]
0x180044856  call    ?AddDataAttribute@SetStringIter@@QEAAJUModifyContext@1@PEBG1@Z; SetStringIter::AddDataAttribute(SetStringIter::ModifyContext,ushort const *,ushort const *)
0x18004485b  mov     ebx, eax
0x18004485d  jmp     loc_1800449B8
0x180044862  mov     ebx, 1
0x180044867  jmp     loc_1800449B8
0x18004486c  test    ebx, ebx
0x18004486e  js      loc_1800449B8
0x180044874  mov     rcx, [r13+0]
0x180044878  lea     r8, [rbp+57h+var_60]
0x18004487c  movaps  xmm0, [rbp+57h+var_90]
0x180044880  lea     rdx, [rbp+57h+var_90]
0x180044884  movdqa  [rbp+57h+var_90], xmm0
0x180044889  mov     rax, [rcx]
0x18004488c  mov     rax, [rax+38h]
0x180044890  call    cs:__guard_dispatch_icall_fptr
0x180044896  test    eax, eax
0x180044898  js      loc_180044993
0x18004489e  movaps  xmm0, [rbp+57h+var_60]
0x1800448a2  lea     r8, [rbp+57h+lpMem]
0x1800448a6  mov     rcx, [rdi+40h]
0x1800448aa  lea     rdx, [rbp+57h+var_90]
0x1800448ae  movdqa  [rbp+57h+var_90], xmm0
0x1800448b3  call    RtlMicrodomUpdateGetCookieForExistingAttribute
0x1800448b8  test    eax, eax
0x1800448ba  js      loc_180044977
0x1800448c0  mov     rcx, [rdi+48h]; unsigned __int16 *
0x1800448c4  mov     rsi, r15
0x1800448c7  test    rcx, rcx
0x1800448ca  jz      short loc_1800448E5
0x1800448cc  lea     rdx, [rbp+57h+var_50]; struct _LUTF8_STRING *
0x1800448d0  call    ?UnicodeToUtf8@@YAJPEBGPEAU_LUTF8_STRING@@@Z; UnicodeToUtf8(ushort const *,_LUTF8_STRING *)
0x1800448d5  mov     ebx, eax
0x1800448d7  test    eax, eax
0x1800448d9  js      loc_180044993
0x1800448df  lea     rsi, [rbp+57h+var_50]
0x1800448e3  jmp     short loc_1800448E8
0x1800448e5  mov     ebx, r15d
0x1800448e8  test    ebx, ebx
0x1800448ea  js      loc_180044993
0x1800448f0  test    rsi, rsi
0x1800448f3  jz      short loc_18004490E
0x1800448f5  mov     rdx, [rbp+57h+lpMem]
0x1800448f9  mov     r8, rsi
0x1800448fc  mov     rcx, [rdi+40h]
0x180044900  call    RtlMicrodomUpdateSetNodeTextContent
0x180044905  test    eax, eax
0x180044907  js      short loc_18004494B
0x180044909  mov     ebx, r15d
0x18004490c  jmp     short loc_180044967
0x18004490e  movaps  xmm0, xmmword ptr [r12]
0x180044913  lea     r9, [rbp+57h+var_A0]
0x180044917  lea     r8, [rbp+57h+var_90]
0x18004491b  movdqa  [rbp+57h+var_90], xmm0
0x180044920  mov     rdx, r13
0x180044923  mov     rcx, rdi
0x180044926  call    ?GetModifyContext@SetStringIter@@QEAAJAEAVUnattend@@VUnattendNode@@AEAUModifyContext@1@@Z; SetStringIter::GetModifyContext(Unattend &,UnattendNode,SetStringIter::ModifyContext &)
0x18004492b  mov     ebx, eax
0x18004492d  test    eax, eax
0x18004492f  js      short loc_180044993
0x180044931  mov     r8, [rbp+57h+lpMem]
0x180044935  mov     rdx, [rbp+57h+var_A0]
0x180044939  mov     rcx, [rdi+40h]
0x18004493d  call    RtlMicrodomUpdateRemoveChild
0x180044942  test    eax, eax
0x180044944  js      short loc_18004494B
0x180044946  mov     ebx, r15d
0x180044949  jmp     short loc_180044993
0x18004494b  mov     ecx, eax; Status
0x18004494d  call    cs:__imp_RtlNtStatusToDosError
0x180044954  nop     dword ptr [rax+rax+00h]
0x180044959  movzx   ebx, ax
0x18004495c  or      ebx, 80070000h
0x180044962  test    eax, eax
0x180044964  cmovle  ebx, eax
0x180044967  test    rsi, rsi
0x18004496a  jz      short loc_180044993
0x18004496c  lea     rcx, [rbp+57h+var_50]; struct _LUTF8_STRING *
0x180044970  call    ?FreeUtf8@@YAJPEAU_LUTF8_STRING@@@Z; FreeUtf8(_LUTF8_STRING *)
0x180044975  jmp     short loc_180044993
0x180044977  mov     ecx, eax; Status
0x180044979  call    cs:__imp_RtlNtStatusToDosError
0x180044980  nop     dword ptr [rax+rax+00h]
0x180044985  movzx   ebx, ax
0x180044988  or      ebx, 80070000h
0x18004498e  test    eax, eax
0x180044990  cmovle  ebx, eax
0x180044993  test    r14, r14
0x180044996  jz      short loc_1800449B8
0x180044998  call    cs:__imp_GetProcessHeap
0x18004499f  nop     dword ptr [rax+rax+00h]
0x1800449a4  mov     r8, r14; lpMem
0x1800449a7  xor     edx, edx; dwFlags
0x1800449a9  mov     rcx, rax; hHeap
0x1800449ac  call    cs:__imp_HeapFree
0x1800449b3  nop     dword ptr [rax+rax+00h]
0x1800449b8  mov     eax, ebx
0x1800449ba  mov     rcx, [rbp+57h+var_38]
0x1800449be  xor     rcx, rsp; StackCookie
0x1800449c1  call    __security_check_cookie
0x1800449c6  mov     rbx, [rsp+0E0h+arg_18]
0x1800449ce  add     rsp, 0B0h
0x1800449d5  pop     r15
0x1800449d7  pop     r14
0x1800449d9  pop     r13
0x1800449db  pop     r12
0x1800449dd  pop     rdi
0x1800449de  pop     rsi
0x1800449df  pop     rbp
0x1800449e0  retn
```
