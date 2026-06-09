# ConvertPrintQueuePropertyToDevProperty(_PrintQueueProperty &,_DEVPROPERTY &)

- ea: `0x180015aa4`
- end: `0x180015c5e`
- name: `?ConvertPrintQueuePropertyToDevProperty@@YAJAEAU_PrintQueueProperty@@AEAU_DEVPROPERTY@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(struct _PrintQueueProperty *, struct _DEVPROPERTY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012bd0`

## callees

- `0x180001bb0`
- `0x180001e20`
- `0x180015aa4`
- `0x1800167c4`
- `0x180016800`
- `0x1800168a8`
- `0x180016a3c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180015b8e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180015b8e`

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
  v17 = &qword_18001C1B8;
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
0x180015aa4  push    rbx
0x180015aa6  push    rbp
0x180015aa7  push    rsi
0x180015aa8  push    rdi
0x180015aa9  push    r14
0x180015aab  sub     rsp, 40h
0x180015aaf  movups  xmm0, xmmword ptr [rcx]
0x180015ab2  xor     r14d, r14d
0x180015ab5  mov     rsi, rcx
0x180015ab8  mov     rdi, rdx
0x180015abb  mov     ebx, r14d
0x180015abe  movups  xmmword ptr [rdx], xmm0
0x180015ac1  mov     eax, [rcx+10h]
0x180015ac4  mov     [rdx+10h], eax
0x180015ac7  mov     [rdx+14h], r14d
0x180015acb  mov     [rdx+18h], r14
0x180015acf  mov     eax, [rcx+14h]
0x180015ad2  mov     [rdx+20h], eax
0x180015ad5  mov     ecx, [rcx+14h]
0x180015ad8  sub     ecx, 7
0x180015adb  jz      loc_180015C2B
0x180015ae1  sub     ecx, 0Ah
0x180015ae4  jz      loc_180015C07
0x180015aea  sub     ecx, 1
0x180015aed  jz      loc_180015BC6
0x180015af3  sub     ecx, 1
0x180015af6  jz      loc_180015B8A
0x180015afc  cmp     ecx, 1FFFh
0x180015b02  jz      short loc_180015B0E
0x180015b04  mov     ebx, 8007070Ch
0x180015b09  jmp     loc_180015C50
0x180015b0e  mov     rdx, [rsi+18h]; unsigned __int16 *
0x180015b12  lea     rbp, ?gszzEmpty@TMultiString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TMultiString::gszzEmpty
0x180015b19  mov     [rsp+68h+var_48], 7274736Dh
0x180015b21  mov     [rsp+68h+var_40], rbp
0x180015b26  mov     [rsp+68h+var_38], r14d
0x180015b2b  test    rdx, rdx
0x180015b2e  jz      short loc_180015B3F
0x180015b30  lea     rcx, [rsp+68h+var_48]; this
0x180015b35  call    ?Update@TMultiString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TMultiString::Update(ushort const *)
0x180015b3a  mov     rbp, [rsp+68h+var_40]
0x180015b3f  mov     rcx, rbp; this
0x180015b42  call    ?MultiSzSize@NCoreLibrary@@YAIPEBG@Z; NCoreLibrary::MultiSzSize(ushort const *)
0x180015b47  cmp     eax, 2
0x180015b4a  ja      short loc_180015B53
0x180015b4c  mov     ebx, 80070057h
0x180015b51  jmp     short loc_180015B7D
0x180015b53  lea     ecx, [rax+rax]
0x180015b56  mov     [rdi+24h], ecx
0x180015b59  call    DllAllocSplMem
0x180015b5e  mov     [rdi+28h], rax
0x180015b62  test    rax, rax
0x180015b65  jnz     short loc_180015B6E
0x180015b67  mov     ebx, 8007000Eh
0x180015b6c  jmp     short loc_180015B7D
0x180015b6e  mov     r8d, [rdi+24h]; Size
0x180015b72  mov     rdx, rbp; Src
0x180015b75  mov     rcx, rax; void *
0x180015b78  call    memcpy_0
0x180015b7d  mov     rdx, rbp; void *
0x180015b80  call    ?vFree@TMultiString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TMultiString::vFree(void *)
0x180015b85  jmp     loc_180015C50
0x180015b8a  mov     rcx, [rsi+18h]; pSecurityDescriptor
0x180015b8e  call    cs:__imp_GetSecurityDescriptorLength
0x180015b95  nop     dword ptr [rax+rax+00h]
0x180015b9a  mov     ecx, eax
0x180015b9c  mov     [rdi+24h], eax
0x180015b9f  call    DllAllocSplMem
0x180015ba4  mov     [rdi+28h], rax
0x180015ba8  test    rax, rax
0x180015bab  jz      loc_180015C4B
0x180015bb1  mov     r8d, [rdi+24h]; Size
0x180015bb5  mov     rcx, rax; void *
0x180015bb8  mov     rdx, [rsi+18h]; Src
0x180015bbc  call    memcpy_0
0x180015bc1  jmp     loc_180015C50
0x180015bc6  cmp     [rsi+18h], r14
0x180015bca  lea     rcx, qword_18001C1B8
0x180015bd1  cmovnz  rcx, [rsi+18h]
0x180015bd6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015bda  inc     rax
0x180015bdd  cmp     [rcx+rax*2], r14w
0x180015be2  jnz     short loc_180015BDA
0x180015be4  lea     eax, ds:2[rax*2]
0x180015beb  mov     [rdx+24h], eax
0x180015bee  call    AllocSplStr
0x180015bf3  mov     [rdi+28h], rax
0x180015bf7  mov     ebx, 8007000Eh
0x180015bfc  neg     rax
0x180015bff  sbb     ecx, ecx
0x180015c01  not     ecx
0x180015c03  and     ebx, ecx
0x180015c05  jmp     short loc_180015C50
0x180015c07  mov     ecx, 1
0x180015c0c  mov     [rdx+24h], ecx
0x180015c0f  call    DllAllocSplMem
0x180015c14  mov     [rdi+28h], rax
0x180015c18  mov     rdx, rax
0x180015c1b  test    rax, rax
0x180015c1e  jz      short loc_180015C4B
0x180015c20  mov     eax, [rsi+18h]
0x180015c23  neg     eax
0x180015c25  sbb     cl, cl
0x180015c27  mov     [rdx], cl
0x180015c29  jmp     short loc_180015C50
0x180015c2b  mov     ecx, 4
0x180015c30  mov     [rdx+24h], ecx
0x180015c33  call    DllAllocSplMem
0x180015c38  mov     [rdi+28h], rax
0x180015c3c  mov     rcx, rax
0x180015c3f  test    rax, rax
0x180015c42  jz      short loc_180015C4B
0x180015c44  mov     eax, [rsi+18h]
0x180015c47  mov     [rcx], eax
0x180015c49  jmp     short loc_180015C50
0x180015c4b  mov     ebx, 8007000Eh
0x180015c50  mov     eax, ebx
0x180015c52  add     rsp, 40h
0x180015c56  pop     r14
0x180015c58  pop     rdi
0x180015c59  pop     rsi
0x180015c5a  pop     rbp
0x180015c5b  pop     rbx
0x180015c5c  retn
```
