# ConvertPrintQueuePropertyToDevProperty(_PrintQueueProperty &,_DEVPROPERTY &)

- ea: `0x1800141a4`
- end: `0x180014357`
- name: `?ConvertPrintQueuePropertyToDevProperty@@YAJAEAU_PrintQueueProperty@@AEAU_DEVPROPERTY@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(struct _PrintQueueProperty *, struct _DEVPROPERTY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800114cc`

## callees

- `0x180001ba0`
- `0x180001dc0`
- `0x1800141a4`
- `0x180014dbc`
- `0x180014df8`
- `0x180014ea0`
- `0x18001503c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001428e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001428e`

## pseudocode

```c
__int64 __fastcall ConvertPrintQueuePropertyToDevProperty(struct _PrintQueueProperty *a1, struct _DEVPROPERTY *a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  const unsigned __int16 *v9; // rdx
  NCoreLibrary *v10; // rbp
  unsigned int v11; // eax
  NCoreLibrary::TMultiString *v12; // rcx
  __int64 v13; // rcx
  void *v14; // rax
  ULONG SecurityDescriptorLength; // eax
  void *v16; // rax
  __int64 *v17; // rcx
  __int64 v18; // rax
  void *v19; // rax
  _BYTE *v20; // rax
  _DWORD *v21; // rax
  int v23; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 near **v24; // [rsp+28h] [rbp-40h]
  int v25; // [rsp+30h] [rbp-38h]

  v4 = 0;
  a2->CompKey.Key.fmtid = *(DEVPROPGUID *)a1;
  a2->CompKey.Key.pid = *((_DWORD *)a1 + 4);
  a2->CompKey.Store = DEVPROP_STORE_SYSTEM;
  a2->CompKey.LocaleName = 0;
  a2->Type = *((_DWORD *)a1 + 5);
  v5 = *((_DWORD *)a1 + 5) - 7;
  if ( !v5 )
  {
    a2->BufferSize = 4;
    v21 = (_DWORD *)DllAllocSplMem(4);
    a2->Buffer = v21;
    if ( v21 )
    {
      *v21 = *((_DWORD *)a1 + 6);
      return v4;
    }
    return (unsigned int)-2147024882;
  }
  v6 = v5 - 10;
  if ( !v6 )
  {
    a2->BufferSize = 1;
    v20 = (_BYTE *)DllAllocSplMem(1);
    a2->Buffer = v20;
    if ( v20 )
    {
      *v20 = -(*((_DWORD *)a1 + 6) != 0);
      return v4;
    }
    return (unsigned int)-2147024882;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 == 0x1FFF )
      {
        v9 = (const unsigned __int16 *)*((_QWORD *)a1 + 3);
        v10 = (NCoreLibrary *)&NCoreLibrary::TMultiString::gszzEmpty;
        v23 = 1920234349;
        v24 = &NCoreLibrary::TMultiString::gszzEmpty;
        v25 = 0;
        if ( v9 )
        {
          NCoreLibrary::TMultiString::Update((NCoreLibrary::TMultiString *)&v23, v9);
          v10 = (NCoreLibrary *)v24;
        }
        v11 = NCoreLibrary::MultiSzSize(v10, v9);
        if ( v11 > 2 )
        {
          v13 = 2 * v11;
          a2->BufferSize = v13;
          v14 = (void *)DllAllocSplMem(v13);
          a2->Buffer = v14;
          if ( v14 )
            memcpy_0(v14, v10, a2->BufferSize);
          else
            v4 = -2147024882;
        }
        else
        {
          v4 = -2147024809;
        }
        NCoreLibrary::TMultiString::vFree(v12, v10);
      }
      else
      {
        return (unsigned int)-2147023092;
      }
      return v4;
    }
    SecurityDescriptorLength = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)a1 + 3));
    a2->BufferSize = SecurityDescriptorLength;
    v16 = (void *)DllAllocSplMem(SecurityDescriptorLength);
    a2->Buffer = v16;
    if ( v16 )
    {
      memcpy_0(v16, *((const void **)a1 + 3), a2->BufferSize);
      return v4;
    }
    return (unsigned int)-2147024882;
  }
  v17 = qword_18001B1B0;
  if ( *((_QWORD *)a1 + 3) )
    v17 = (__int64 *)*((_QWORD *)a1 + 3);
  v18 = -1;
  do
    ++v18;
  while ( *((_WORD *)v17 + v18) );
  a2->BufferSize = 2 * v18 + 2;
  v19 = (void *)AllocSplStr();
  a2->Buffer = v19;
  return v19 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1800141a4  push    rbx
0x1800141a6  push    rbp
0x1800141a7  push    rsi
0x1800141a8  push    rdi
0x1800141a9  push    r14
0x1800141ab  sub     rsp, 40h
0x1800141af  movups  xmm0, xmmword ptr [rcx]
0x1800141b2  xor     r14d, r14d
0x1800141b5  mov     rsi, rcx
0x1800141b8  mov     rdi, rdx
0x1800141bb  mov     ebx, r14d
0x1800141be  movups  xmmword ptr [rdx], xmm0
0x1800141c1  mov     eax, [rcx+10h]
0x1800141c4  mov     [rdx+10h], eax
0x1800141c7  mov     [rdx+14h], r14d
0x1800141cb  mov     [rdx+18h], r14
0x1800141cf  mov     eax, [rcx+14h]
0x1800141d2  mov     [rdx+20h], eax
0x1800141d5  mov     ecx, [rcx+14h]
0x1800141d8  sub     ecx, 7
0x1800141db  jz      loc_180014325
0x1800141e1  sub     ecx, 0Ah
0x1800141e4  jz      loc_180014301
0x1800141ea  sub     ecx, 1
0x1800141ed  jz      loc_1800142C0
0x1800141f3  sub     ecx, 1
0x1800141f6  jz      loc_18001428A
0x1800141fc  cmp     ecx, 1FFFh
0x180014202  jz      short loc_18001420E
0x180014204  mov     ebx, 8007070Ch
0x180014209  jmp     loc_18001434A
0x18001420e  mov     rdx, [rsi+18h]; unsigned __int16 *
0x180014212  lea     rbp, ?gszzEmpty@TMultiString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TMultiString::gszzEmpty
0x180014219  mov     [rsp+68h+var_48], 7274736Dh
0x180014221  mov     [rsp+68h+var_40], rbp
0x180014226  mov     [rsp+68h+var_38], r14d
0x18001422b  test    rdx, rdx
0x18001422e  jz      short loc_18001423F
0x180014230  lea     rcx, [rsp+68h+var_48]; this
0x180014235  call    ?Update@TMultiString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TMultiString::Update(ushort const *)
0x18001423a  mov     rbp, [rsp+68h+var_40]
0x18001423f  mov     rcx, rbp; this
0x180014242  call    ?MultiSzSize@NCoreLibrary@@YAIPEBG@Z; NCoreLibrary::MultiSzSize(ushort const *)
0x180014247  cmp     eax, 2
0x18001424a  ja      short loc_180014253
0x18001424c  mov     ebx, 80070057h
0x180014251  jmp     short loc_18001427D
0x180014253  lea     ecx, [rax+rax]
0x180014256  mov     [rdi+24h], ecx
0x180014259  call    DllAllocSplMem
0x18001425e  mov     [rdi+28h], rax
0x180014262  test    rax, rax
0x180014265  jnz     short loc_18001426E
0x180014267  mov     ebx, 8007000Eh
0x18001426c  jmp     short loc_18001427D
0x18001426e  mov     r8d, [rdi+24h]; Size
0x180014272  mov     rdx, rbp; Src
0x180014275  mov     rcx, rax; void *
0x180014278  call    memcpy_0
0x18001427d  mov     rdx, rbp; void *
0x180014280  call    ?vFree@TMultiString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TMultiString::vFree(void *)
0x180014285  jmp     loc_18001434A
0x18001428a  mov     rcx, [rsi+18h]; pSecurityDescriptor
0x18001428e  call    cs:__imp_GetSecurityDescriptorLength
0x180014294  mov     ecx, eax
0x180014296  mov     [rdi+24h], eax
0x180014299  call    DllAllocSplMem
0x18001429e  mov     [rdi+28h], rax
0x1800142a2  test    rax, rax
0x1800142a5  jz      loc_180014345
0x1800142ab  mov     r8d, [rdi+24h]; Size
0x1800142af  mov     rcx, rax; void *
0x1800142b2  mov     rdx, [rsi+18h]; Src
0x1800142b6  call    memcpy_0
0x1800142bb  jmp     loc_18001434A
0x1800142c0  cmp     [rsi+18h], r14
0x1800142c4  lea     rcx, qword_18001B1B0
0x1800142cb  cmovnz  rcx, [rsi+18h]
0x1800142d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800142d4  inc     rax
0x1800142d7  cmp     [rcx+rax*2], r14w
0x1800142dc  jnz     short loc_1800142D4
0x1800142de  lea     eax, ds:2[rax*2]
0x1800142e5  mov     [rdx+24h], eax
0x1800142e8  call    AllocSplStr
0x1800142ed  mov     [rdi+28h], rax
0x1800142f1  mov     ebx, 8007000Eh
0x1800142f6  neg     rax
0x1800142f9  sbb     ecx, ecx
0x1800142fb  not     ecx
0x1800142fd  and     ebx, ecx
0x1800142ff  jmp     short loc_18001434A
0x180014301  mov     ecx, 1
0x180014306  mov     [rdx+24h], ecx
0x180014309  call    DllAllocSplMem
0x18001430e  mov     [rdi+28h], rax
0x180014312  mov     rdx, rax
0x180014315  test    rax, rax
0x180014318  jz      short loc_180014345
0x18001431a  mov     eax, [rsi+18h]
0x18001431d  neg     eax
0x18001431f  sbb     cl, cl
0x180014321  mov     [rdx], cl
0x180014323  jmp     short loc_18001434A
0x180014325  mov     ecx, 4
0x18001432a  mov     [rdx+24h], ecx
0x18001432d  call    DllAllocSplMem
0x180014332  mov     [rdi+28h], rax
0x180014336  mov     rcx, rax
0x180014339  test    rax, rax
0x18001433c  jz      short loc_180014345
0x18001433e  mov     eax, [rsi+18h]
0x180014341  mov     [rcx], eax
0x180014343  jmp     short loc_18001434A
0x180014345  mov     ebx, 8007000Eh
0x18001434a  mov     eax, ebx
0x18001434c  add     rsp, 40h
0x180014350  pop     r14
0x180014352  pop     rdi
0x180014353  pop     rsi
0x180014354  pop     rbp
0x180014355  pop     rbx
0x180014356  retn
```
