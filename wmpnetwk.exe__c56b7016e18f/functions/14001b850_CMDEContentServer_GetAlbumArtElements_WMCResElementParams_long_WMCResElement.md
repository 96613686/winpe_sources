# CMDEContentServer::GetAlbumArtElements(_WMCResElementParams *,long *,_WMCResElement * *)

- ea: `0x14001b850`
- end: `0x14001bee3`
- name: `?GetAlbumArtElements@CMDEContentServer@@UEAAJPEAU_WMCResElementParams@@PEAJPEAPEAU_WMCResElement@@@Z`
- size: `1683`
- prototype: `int(CMDEContentServer *__hidden this, struct _WMCResElementParams *, int *, struct _WMCResElement **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1400030e8`
- `0x140005b38`
- `0x140014f90`
- `0x14001b560`
- `0x14001b850`
- `0x14001d520`
- `0x14001e384`
- `0x14001e3ec`
- `0x14003b2b8`
- `0x140046020`
- `0x14004639c`
- `0x1400547b0`
- `0x140057bc4`
- `0x140090d94`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14001b893`
- `KERNEL32!EnterCriticalSection` at `0x14001b893`
- `KERNEL32!LeaveCriticalSection` at `0x14001ba80`
- `KERNEL32!LeaveCriticalSection` at `0x14001ba80`
- `KERNEL32!CompareStringOrdinal` at `0x14001bb90`
- `KERNEL32!CompareStringOrdinal` at `0x14001bb90`
- `OLEAUT32!__imp_SysFreeString` at `0x14001bc10`
- `OLEAUT32!__imp_SysFreeString` at `0x14001bc1a`
- `OLEAUT32!__imp_SysFreeString` at `0x14001bc24`
- `OLEAUT32!__imp_SysFreeString` at `0x14001bc2e`
- `OLEAUT32!__imp_SysFreeString` at `0x14001bc10`
- `OLEAUT32!__imp_SysFreeString` at `0x14001bc1a`
- `OLEAUT32!__imp_SysFreeString` at `0x14001bc24`
- `OLEAUT32!__imp_SysFreeString` at `0x14001bc2e`

## pseudocode

```c
__int64 __fastcall CMDEContentServer::GetAlbumArtElements(
        CMDEContentServer *this,
        struct _WMCResElementParams *a2,
        int *a3,
        struct _WMCResElement **a4)
{
  struct _WMCResElement **v6; // r15
  int *v7; // r9
  char *v8; // r12
  PVOID *v9; // rax
  unsigned __int64 v10; // rcx
  int v11; // ebp
  _QWORD *v12; // rdi
  __int64 v13; // rsi
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  const WCHAR *v18; // rcx
  volatile signed __int32 *v19; // r15
  __int64 v20; // rbx
  signed __int32 v21; // ecx
  bool v22; // cc
  int ImageTranscodingResElement; // eax
  BSTR *v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // r10
  __int64 v29; // r11
  _OWORD *v30; // rax
  __int64 v31; // rcx
  int v32; // ebx
  __int64 v33; // rdx
  int *v34; // rsi
  struct _WMCResElement *v35; // rdi
  struct _WMCResElement *v36; // rcx
  int v37; // eax
  unsigned int v38; // eax
  char v39[16]; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int64 v40; // [rsp+70h] [rbp-58h]
  __int128 v41; // [rsp+78h] [rbp-50h]
  int v42; // [rsp+88h] [rbp-40h]
  __int64 v43; // [rsp+D0h] [rbp+8h] BYREF
  int *v44; // [rsp+E0h] [rbp+18h]
  struct _WMCResElement **v45; // [rsp+E8h] [rbp+20h]

  v45 = a4;
  v44 = a3;
  v6 = a4;
  v7 = a3;
  if ( this )
  {
    v8 = (char *)this + 8;
    if ( this != (CMDEContentServer *)-8LL )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v7 = v44;
    }
  }
  else
  {
    v8 = 0;
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
  {
    McTemplateU0qq_EventWriteTransfer(this, MDE_Generate_Album_Art_Element_Start, 0, 0);
    v7 = v44;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    if ( a2 )
    {
      v25 = *((_QWORD *)a2 + 5);
      v26 = *((_QWORD *)a2 + 4);
      v27 = *((_QWORD *)a2 + 3);
      v28 = *((_QWORD *)a2 + 2);
      v29 = *(_QWORD *)a2;
    }
    else
    {
      v25 = 0;
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v29 = 0;
    }
    v34 = v44;
    WPP_SF_qSSSSSqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, v28, v27, v26, v25, (char)v44, (char)v6);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v7 = v34;
  }
  v10 = 0;
  v40 = 0;
  v42 = 10;
  *(_OWORD *)v39 = 0;
  v41 = 0;
  if ( !a2 || !v7 || !v6 )
  {
    v11 = -2147024809;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    {
      WPP_SF_qqq(v9[2], 102, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, a2, v7, v6);
LABEL_12:
      v10 = v40;
    }
    goto LABEL_26;
  }
  *v7 = 0;
  v11 = 0;
  *v6 = 0;
  v12 = (_QWORD *)*((_QWORD *)this + 19);
  if ( !v12 )
    goto LABEL_68;
  do
  {
    if ( v11 < 0 )
      goto LABEL_66;
    v13 = v12[2];
    v12 = (_QWORD *)*v12;
    if ( (*((_DWORD *)this + 112) || *(_DWORD *)(v13 + 56) != 1)
      && !*(_DWORD *)(v13 + 56)
      && (*((_BYTE *)a2 + 128) & 1) == 0
      && !*(_DWORD *)(v13 + 64)
      && !*(_DWORD *)(v13 + 60)
      && (unsigned int)CMDEContentServer::ProfileMatchesMIME(
                         (const struct MDEProfile *)v13,
                         *(const unsigned __int16 **)a2) )
    {
      v15 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
      v16 = *((_QWORD *)this + 50);
      v17 = v15 + 24;
      v18 = (const WCHAR *)(v16 - 24);
      v43 = v15 + 24;
      v19 = (volatile signed __int32 *)v15;
      if ( v16 - 24 != v15 )
      {
        if ( *(int *)(v15 + 16) >= 0 && *(_QWORD *)v18 == *(_QWORD *)v15 )
        {
          v20 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v18);
          v21 = _InterlockedExchangeAdd(v19 + 4, 0xFFFFFFFF);
          v22 = v21 <= 1;
          v18 = (const WCHAR *)(unsigned int)(v21 - 1);
          if ( v22 )
            (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19, v19);
          v17 = v20 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v43, v16, *(unsigned int *)(v16 - 16));
          v17 = v43;
        }
      }
      if ( *(_DWORD *)(v13 + 20) )
      {
        if ( *(_DWORD *)(v13 + 104) > 0xA0u
          || *(_DWORD *)(v13 + 108) > 0xA0u
          || CompareStringOrdinal(*(LPCWCH *)(v13 + 40), -1, L"JPEG_TN", -1, 0) != 2 )
        {
LABEL_41:
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 - 24 + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v17 - 24) + 8LL))(*(_QWORD *)(v17 - 24));
          continue;
        }
        ImageTranscodingResElement = CMDEContentServer::GenerateImageTranscodingResElement(
                                       a2,
                                       (struct MDEProfile *)v13,
                                       (__int64)L"http",
                                       v17,
                                       *((_QWORD *)this + 52),
                                       (__int64)L"http-get",
                                       1,
                                       1,
                                       *(_DWORD *)(v13 + 104),
                                       *(_DWORD *)(v13 + 108),
                                       *(_WORD **)(v13 + 40),
                                       (__int64)v39);
      }
      else
      {
        ImageTranscodingResElement = CMDEContentServer::GenerateNonTranscodingResElements(
                                       v18,
                                       (__int64)a2,
                                       (const struct MDEProfile *)v13,
                                       (__int64)L"http",
                                       v17,
                                       *((_QWORD *)this + 52),
                                       (__int64)L"http-get",
                                       L"albumArt=true",
                                       (__int64)v39);
      }
      v11 = ImageTranscodingResElement;
      goto LABEL_41;
    }
  }
  while ( v12 );
  if ( v11 < 0 )
  {
LABEL_66:
    v6 = v45;
    goto LABEL_12;
  }
  v10 = v40;
  if ( v40 )
  {
    if ( v40 <= 0x7FFFFFFF )
    {
      v35 = (struct _WMCResElement *)operator new[](saturated_mul(v40, 0x60u));
      v32 = 0;
      while ( 1 )
      {
        v10 = v40;
        if ( !v40 )
          break;
        v30 = (_OWORD *)ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>>::RemoveHead(v39);
        v31 = v32++;
        v33 = 96 * v31;
        *(_OWORD *)((char *)v35 + v33) = *v30;
        *(_OWORD *)((char *)v35 + v33 + 16) = v30[1];
        *(_OWORD *)((char *)v35 + v33 + 32) = v30[2];
        *(_OWORD *)((char *)v35 + v33 + 48) = v30[3];
        *(_OWORD *)((char *)v35 + v33 + 64) = v30[4];
        *(_OWORD *)((char *)v35 + v33 + 80) = v30[5];
        *(_QWORD *)v30 = 0;
        *((_QWORD *)v30 + 2) = 0;
        *((_QWORD *)v30 + 5) = 0;
        *((_QWORD *)v30 + 6) = 0;
        operator delete(v30);
      }
      v6 = v45;
      *v44 = v32;
      *v6 = v35;
    }
    else
    {
      v6 = v45;
      v11 = -2147024809;
    }
    goto LABEL_26;
  }
  v6 = v45;
LABEL_68:
  v11 = -2147024809;
LABEL_26:
  while ( v10 )
  {
    v24 = (BSTR *)ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>>::RemoveHead(v39);
    SysFreeString(*v24);
    SysFreeString(v24[2]);
    SysFreeString(v24[5]);
    SysFreeString(v24[6]);
    operator delete(v24);
    v10 = v40;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = ((v11 >> 31) & 0xFFFFFFFD) + 5;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)v10 )
    {
      if ( v6 )
        v36 = *v6;
      else
        v36 = 0;
      if ( v44 )
        v37 = *v44;
      else
        v37 = -1;
      WPP_SF_ddq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)v11,
        v37,
        v36);
    }
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
  {
    if ( v44 )
      v38 = *v44;
    else
      v38 = -1;
    McTemplateU0qq_EventWriteTransfer(v10, MDE_Generate_Album_Art_Element_Stop, v38, (unsigned int)v11);
  }
  ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(v39);
  if ( v8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14001b850  mov     rax, rsp
0x14001b853  mov     [rax+20h], r9
0x14001b857  mov     [rax+18h], r8
0x14001b85b  push    r12
0x14001b85d  sub     rsp, 0C0h
0x14001b864  mov     [rax-28h], r13
0x14001b868  mov     r13, rcx
0x14001b86b  mov     [rax-30h], r14
0x14001b86f  mov     r14, rdx
0x14001b872  mov     [rax-38h], r15
0x14001b876  mov     r15, r9
0x14001b879  mov     r9, r8
0x14001b87c  test    rcx, rcx
0x14001b87f  jz      loc_14001BD6E
0x14001b885  lea     r12, [rcx+8]
0x14001b889  test    r12, r12
0x14001b88c  jz      short loc_14001B8A1
0x14001b88e  lea     rcx, [r12+8]; lpCriticalSection
0x14001b893  call    cs:__imp_EnterCriticalSection
0x14001b899  mov     r9, [rsp+0C8h+arg_10]
0x14001b8a1  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14001b8a8  jnz     loc_14001BD76
0x14001b8ae  mov     rax, cs:WPP_GLOBAL_Control
0x14001b8b5  lea     rdx, WPP_GLOBAL_Control
0x14001b8bc  mov     [rsp+0C8h+var_18], rsi
0x14001b8c4  cmp     rax, rdx
0x14001b8c7  jnz     loc_14001BC95
0x14001b8cd  xor     ecx, ecx
0x14001b8cf  mov     [rsp+0C8h+arg_8], rbx
0x14001b8d7  mov     [rsp+0C8h+var_10], rbp
0x14001b8df  xorps   xmm0, xmm0
0x14001b8e2  mov     [rsp+0C8h+var_20], rdi
0x14001b8ea  mov     r8, 0FFFFFFFFFFFFFFFFh
0x14001b8f1  mov     [rsp+0C8h+var_58], rcx
0x14001b8f6  mov     [rsp+0C8h+var_40], 0Ah
0x14001b901  movdqu  xmmword ptr [rsp+0C8h+var_68], xmm0
0x14001b907  movdqu  [rsp+0C8h+var_50], xmm0
0x14001b90d  test    r14, r14
0x14001b910  jnz     loc_14001BCCA
0x14001b916  mov     ebp, 80070057h
0x14001b91b  cmp     rax, rdx
0x14001b91e  jz      loc_14001BA08
0x14001b924  test    byte ptr [rax+1Ch], 2
0x14001b928  jz      loc_14001BA08
0x14001b92e  cmp     byte ptr [rax+19h], 2
0x14001b932  jb      loc_14001BA08
0x14001b938  mov     rcx, [rax+10h]
0x14001b93c  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14001b943  mov     [rsp+0C8h+var_A0], r15
0x14001b948  mov     edx, 66h ; 'f'
0x14001b94d  mov     qword ptr [rsp+0C8h+bIgnoreCase], r9
0x14001b952  mov     r9, r14
0x14001b955  call    WPP_SF_qqq
0x14001b95a  mov     rcx, [rsp+0C8h+var_58]
0x14001b95f  jmp     loc_14001BA08
0x14001b964  mov     [r9], ecx
0x14001b967  xor     ebp, ebp
0x14001b969  mov     [r15], rcx
0x14001b96c  mov     rdi, [r13+98h]
0x14001b973  test    rdi, rdi
0x14001b976  jz      loc_14001BE48
0x14001b97c  nop     dword ptr [rax+00h]
0x14001b980  test    ebp, ebp
0x14001b982  js      loc_14001BE33
0x14001b988  cmp     dword ptr [r13+1C0h], 0
0x14001b990  mov     rsi, [rdi+10h]
0x14001b994  mov     rdi, [rdi]
0x14001b997  jz      loc_14001BB59
0x14001b99d  cmp     dword ptr [rsi+38h], 0
0x14001b9a1  jnz     short loc_14001B9D3
0x14001b9a3  test    byte ptr [r14+80h], 1
0x14001b9ab  jnz     short loc_14001B9D3
0x14001b9ad  cmp     dword ptr [rsi+40h], 0
0x14001b9b1  jnz     short loc_14001B9D3
0x14001b9b3  cmp     dword ptr [rsi+3Ch], 0
0x14001b9b7  jnz     short loc_14001B9D3
0x14001b9b9  mov     rdx, [r14]; unsigned __int16 *
0x14001b9bc  mov     rcx, rsi; struct MDEProfile *
0x14001b9bf  call    ?ProfileMatchesMIME@CMDEContentServer@@CAHPEBUMDEProfile@@PEBG@Z; CMDEContentServer::ProfileMatchesMIME(MDEProfile const *,ushort const *)
0x14001b9c4  test    eax, eax
0x14001b9c6  jnz     loc_14001BA9A
0x14001b9cc  mov     r8, 0FFFFFFFFFFFFFFFFh
0x14001b9d3  test    rdi, rdi
0x14001b9d6  jnz     short loc_14001B980
0x14001b9d8  test    ebp, ebp
0x14001b9da  js      loc_14001BE33
0x14001b9e0  mov     rcx, [rsp+0C8h+var_58]
0x14001b9e5  test    rcx, rcx
0x14001b9e8  jz      loc_14001BE40
0x14001b9ee  cmp     rcx, 7FFFFFFFh
0x14001b9f5  jbe     loc_14001BE13
0x14001b9fb  mov     r15, [rsp+0C8h+arg_18]
0x14001ba03  mov     ebp, 80070057h
0x14001ba08  mov     r14, [rsp+0C8h+var_30]
0x14001ba10  mov     r13, [rsp+0C8h+var_28]
0x14001ba18  mov     rdi, [rsp+0C8h+var_20]
0x14001ba20  mov     rsi, [rsp+0C8h+var_18]
0x14001ba28  test    rcx, rcx
0x14001ba2b  jnz     loc_14001BC00
0x14001ba31  mov     r10, cs:WPP_GLOBAL_Control
0x14001ba38  lea     rax, WPP_GLOBAL_Control
0x14001ba3f  mov     rbx, [rsp+0C8h+arg_8]
0x14001ba47  cmp     r10, rax
0x14001ba4a  jz      short loc_14001BA57
0x14001ba4c  test    byte ptr [r10+1Ch], 1
0x14001ba51  jnz     loc_14001BE52
0x14001ba57  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14001ba5e  mov     r15, [rsp+0C8h+var_38]
0x14001ba66  jnz     loc_14001BEB3
0x14001ba6c  lea     rcx, [rsp+0C8h+var_68]
0x14001ba71  call    ?RemoveAll@?$CAtlList@Usockaddr_storage@@V?$CElementTraits@Usockaddr_storage@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<sockaddr_storage,ATL::CElementTraits<sockaddr_storage>>::RemoveAll(void)
0x14001ba76  test    r12, r12
0x14001ba79  jz      short loc_14001BA86
0x14001ba7b  lea     rcx, [r12+8]; lpCriticalSection
0x14001ba80  call    cs:__imp_LeaveCriticalSection
0x14001ba86  mov     eax, ebp
0x14001ba88  mov     rbp, [rsp+0C8h+var_10]
0x14001ba90  add     rsp, 0C0h
0x14001ba97  pop     r12
0x14001ba99  retn
0x14001ba9a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001baa1  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001baa8  mov     rax, [rax+18h]
0x14001baac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bab1  mov     rdx, [r13+190h]
0x14001bab8  lea     rbx, [rax+18h]
0x14001babc  lea     rcx, [rdx-18h]
0x14001bac0  mov     [rsp+0C8h+arg_0], rbx
0x14001bac8  lea     r15, [rbx-18h]
0x14001bacc  cmp     rcx, r15
0x14001bacf  jz      short loc_14001BB16
0x14001bad1  cmp     dword ptr [r15+10h], 0
0x14001bad6  jl      loc_14001BDF5
0x14001badc  mov     rax, [r15]
0x14001badf  cmp     [rcx], rax
0x14001bae2  jnz     loc_14001BDF5
0x14001bae8  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001baed  mov     rbx, rax
0x14001baf0  mov     ecx, 0FFFFFFFFh
0x14001baf5  lock xadd [r15+10h], ecx
0x14001bafb  sub     ecx, 1
0x14001bafe  jg      short loc_14001BB12
0x14001bb00  mov     rcx, [r15]
0x14001bb03  mov     rdx, r15
0x14001bb06  mov     r8, [rcx]
0x14001bb09  mov     rax, [r8+8]
0x14001bb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bb12  add     rbx, 18h
0x14001bb16  cmp     dword ptr [rsi+14h], 0
0x14001bb1a  jz      loc_14001BC4B
0x14001bb20  cmp     dword ptr [rsi+68h], 0A0h
0x14001bb27  jbe     short loc_14001BB68
0x14001bb29  mov     r8, 0FFFFFFFFFFFFFFFFh
0x14001bb30  lea     rdx, [rbx-18h]
0x14001bb34  mov     eax, r8d
0x14001bb37  lock xadd [rdx+10h], eax
0x14001bb3c  sub     eax, 1
0x14001bb3f  jg      loc_14001B9D3
0x14001bb45  mov     rcx, [rdx]
0x14001bb48  mov     rax, [rcx]
0x14001bb4b  mov     rax, [rax+8]
0x14001bb4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bb54  jmp     loc_14001B9CC
0x14001bb59  cmp     dword ptr [rsi+38h], 1
0x14001bb5d  jz      loc_14001B9D3
0x14001bb63  jmp     loc_14001B99D
0x14001bb68  cmp     dword ptr [rsi+6Ch], 0A0h
0x14001bb6f  ja      short loc_14001BB29
0x14001bb71  mov     rcx, [rsi+28h]; lpString1
0x14001bb75  lea     r8, aJpegTn; "JPEG_TN"
0x14001bb7c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14001bb83  mov     [rsp+0C8h+bIgnoreCase], 0; bIgnoreCase
0x14001bb8b  mov     r9d, eax; cchCount2
0x14001bb8e  mov     edx, eax; cchCount1
0x14001bb90  call    cs:__imp_CompareStringOrdinal
0x14001bb96  cmp     eax, 2
0x14001bb99  jnz     short loc_14001BB29
0x14001bb9b  lea     rax, [rsp+0C8h+var_68]
0x14001bba0  mov     r9, rbx; __int64
0x14001bba3  mov     qword ptr [rsp+0C8h+var_70], rax; char
0x14001bba8  lea     r8, aHttp_2; "http"
0x14001bbaf  mov     rax, [rsi+28h]
0x14001bbb3  mov     rdx, rsi; struct MDEProfile *
0x14001bbb6  mov     qword ptr [rsp+0C8h+var_78], rax; __int64
0x14001bbbb  mov     rcx, r14; struct _WMCResElementParams *
0x14001bbbe  mov     eax, [rsi+6Ch]
0x14001bbc1  mov     dword ptr [rsp+0C8h+var_80], eax; char
0x14001bbc5  mov     eax, [rsi+68h]
0x14001bbc8  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x14001bbcc  lea     rax, aHttpGet_1; "http-get"
0x14001bbd3  mov     dword ptr [rsp+0C8h+var_90], 1; char
0x14001bbdb  mov     dword ptr [rsp+0C8h+var_98], 1; char
0x14001bbe3  mov     [rsp+0C8h+var_A0], rax; __int64
0x14001bbe8  mov     rax, [r13+1A0h]
0x14001bbef  mov     qword ptr [rsp+0C8h+bIgnoreCase], rax; __int64
0x14001bbf4  call    ?GenerateImageTranscodingResElement@CMDEContentServer@@CAJPEBU_WMCResElementParams@@PEBUMDEProfile@@QEBG222HHKK2PEAV?$CAtlList@PEAU_WMCResElement@@V?$CElementTraits@PEAU_WMCResElement@@@ATL@@@ATL@@@Z; CMDEContentServer::GenerateImageTranscodingResElement(_WMCResElementParams const *,MDEProfile const *,ushort const * const,ushort const * const,ushort const * const,ushort const * const,int,int,ulong,ulong,ushort const * const,ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>> *)
0x14001bbf9  mov     ebp, eax
0x14001bbfb  jmp     loc_14001BB29
0x14001bc00  lea     rcx, [rsp+0C8h+var_68]
0x14001bc05  call    ?RemoveHead@?$CAtlList@PEAU_WMCResElement@@V?$CElementTraits@PEAU_WMCResElement@@@ATL@@@ATL@@QEAAPEAU_WMCResElement@@XZ; ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>>::RemoveHead(void)
0x14001bc0a  mov     rbx, rax
0x14001bc0d  mov     rcx, [rax]; bstrString
0x14001bc10  call    cs:__imp_SysFreeString
0x14001bc16  mov     rcx, [rbx+10h]; bstrString
0x14001bc1a  call    cs:__imp_SysFreeString
0x14001bc20  mov     rcx, [rbx+28h]; bstrString
0x14001bc24  call    cs:__imp_SysFreeString
0x14001bc2a  mov     rcx, [rbx+30h]; bstrString
0x14001bc2e  call    cs:__imp_SysFreeString
0x14001bc34  mov     edx, 60h ; '`'
0x14001bc39  mov     rcx, rbx; Block
0x14001bc3c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001bc41  mov     rcx, [rsp+0C8h+var_58]
0x14001bc46  jmp     loc_14001BA28
0x14001bc4b  lea     rax, [rsp+0C8h+var_68]
0x14001bc50  mov     r8, rsi
0x14001bc53  mov     qword ptr [rsp+0C8h+var_88], rax
0x14001bc58  lea     r9, aHttp_2; "http"
0x14001bc5f  lea     rax, aAlbumartTrue_0; "albumArt=true"
0x14001bc66  mov     rdx, r14
0x14001bc69  mov     qword ptr [rsp+0C8h+var_90], rax
0x14001bc6e  lea     rax, aHttpGet_1; "http-get"
0x14001bc75  mov     qword ptr [rsp+0C8h+var_98], rax
0x14001bc7a  mov     rax, [r13+1A0h]
0x14001bc81  mov     [rsp+0C8h+var_A0], rax
0x14001bc86  mov     qword ptr [rsp+0C8h+bIgnoreCase], rbx
0x14001bc8b  call    ?GenerateNonTranscodingResElements@CMDEContentServer@@AEAAJPEBU_WMCResElementParams@@PEBUMDEProfile@@QEBG2222PEAV?$CAtlList@PEAU_WMCResElement@@V?$CElementTraits@PEAU_WMCResElement@@@ATL@@@ATL@@@Z; CMDEContentServer::GenerateNonTranscodingResElements(_WMCResElementParams const *,MDEProfile const *,ushort const * const,ushort const * const,ushort const * const,ushort const * const,ushort const * const,ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>> *)
0x14001bc90  jmp     loc_14001BBF9
0x14001bc95  test    byte ptr [rax+1Ch], 1
0x14001bc99  jz      loc_14001B8CD
0x14001bc9f  cmp     byte ptr [rax+19h], 5
0x14001bca3  jb      loc_14001B8CD
0x14001bca9  test    r14, r14
0x14001bcac  jz      loc_14001BD95
0x14001bcb2  mov     rcx, [r14+28h]
0x14001bcb6  mov     r8, [r14+20h]
0x14001bcba  mov     r9, [r14+18h]
0x14001bcbe  mov     r10, [r14+10h]
0x14001bcc2  mov     r11, [r14]
0x14001bcc5  jmp     loc_14001BDA3
0x14001bcca  test    r9, r9
0x14001bccd  jz      loc_14001B916
0x14001bcd3  test    r15, r15
0x14001bcd6  jz      loc_14001B916
0x14001bcdc  jmp     loc_14001B964
0x14001bce1  mov     rcx, [rsp+0C8h+var_58]
0x14001bce6  test    rcx, rcx
0x14001bce9  jz      short loc_14001BD54
0x14001bceb  lea     rcx, [rsp+0C8h+var_68]
0x14001bcf0  call    ?RemoveHead@?$CAtlList@PEAU_WMCResElement@@V?$CElementTraits@PEAU_WMCResElement@@@ATL@@@ATL@@QEAAPEAU_WMCResElement@@XZ; ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>>::RemoveHead(void)
0x14001bcf5  movsxd  rcx, ebx
0x14001bcf8  inc     ebx
0x14001bcfa  movups  xmm0, xmmword ptr [rax]
0x14001bcfd  lea     rdx, [rcx+rcx*2]
0x14001bd01  mov     rcx, rax; Block
0x14001bd04  shl     rdx, 5
0x14001bd08  movups  xmmword ptr [rdx+rdi], xmm0
0x14001bd0c  movups  xmm1, xmmword ptr [rax+10h]
0x14001bd10  movups  xmmword ptr [rdx+rdi+10h], xmm1
0x14001bd15  movups  xmm0, xmmword ptr [rax+20h]
0x14001bd19  movups  xmmword ptr [rdx+rdi+20h], xmm0
0x14001bd1e  movups  xmm1, xmmword ptr [rax+30h]
0x14001bd22  movups  xmmword ptr [rdx+rdi+30h], xmm1
0x14001bd27  movups  xmm0, xmmword ptr [rax+40h]
0x14001bd2b  movups  xmmword ptr [rdx+rdi+40h], xmm0
0x14001bd30  movups  xmm1, xmmword ptr [rax+50h]
0x14001bd34  movups  xmmword ptr [rdx+rdi+50h], xmm1
0x14001bd39  mov     edx, 60h ; '`'
0x14001bd3e  mov     [rax], rsi
0x14001bd41  mov     [rax+10h], rsi
0x14001bd45  mov     [rax+28h], rsi
0x14001bd49  mov     [rax+30h], rsi
0x14001bd4d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001bd52  jmp     short loc_14001BCE1
0x14001bd54  mov     rsi, [rsp+0C8h+arg_10]
0x14001bd5c  mov     r15, [rsp+0C8h+arg_18]
0x14001bd64  mov     [rsi], ebx
0x14001bd66  mov     [r15], rdi
0x14001bd69  jmp     loc_14001BA08
0x14001bd6e  xor     r12d, r12d
0x14001bd71  jmp     loc_14001B8A1
0x14001bd76  xor     r9d, r9d
0x14001bd79  lea     rdx, MDE_Generate_Album_Art_Element_Start
0x14001bd80  xor     r8d, r8d
0x14001bd83  call    McTemplateU0qq_EventWriteTransfer
0x14001bd88  mov     r9, [rsp+0C8h+arg_10]
0x14001bd90  jmp     loc_14001B8AE
0x14001bd95  xor     ecx, ecx
0x14001bd97  xor     r8d, r8d
0x14001bd9a  xor     r9d, r9d
0x14001bd9d  xor     r10d, r10d
0x14001bda0  xor     r11d, r11d
0x14001bda3  mov     rsi, [rsp+0C8h+arg_10]
0x14001bdab  mov     edx, 65h ; 'e'
0x14001bdb0  mov     qword ptr [rsp+0C8h+var_78], r15; char
0x14001bdb5  mov     qword ptr [rsp+0C8h+var_80], rsi; char
0x14001bdba  mov     qword ptr [rsp+0C8h+var_88], rcx; __int64
0x14001bdbf  mov     rcx, [rax+10h]; LoggerHandle
0x14001bdc3  mov     qword ptr [rsp+0C8h+var_90], r8; __int64
0x14001bdc8  mov     qword ptr [rsp+0C8h+var_98], r9; __int64
  ... truncated ...
```
