# CLocalUserPage::OnNextButtonClicked(TASKFLOW_TRAVERSAL_FLAGS *,ushort * *)

- ea: `0x18003c5a0`
- end: `0x18003c945`
- name: `?OnNextButtonClicked@CLocalUserPage@@UEAAJPEAW4TASKFLOW_TRAVERSAL_FLAGS@@PEAPEAG@Z`
- size: `933`
- prototype: `int(CLocalUserPage *__hidden this, enum TASKFLOW_TRAVERSAL_FLAGS *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d9a4`
- `0x180026218`
- `0x18003c5a0`
- `0x180053fa8`
- `0x180054014`
- `0x1800540b4`
- `0x180054134`
- `0x18007728a`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c913`
- `DUI70!?EnsureVisible@Element@DirectUI@@QEAA_NXZ` at `0x18003c691`
- `DUI70!?EnsureVisible@Element@DirectUI@@QEAA_NXZ` at `0x18003c7d9`
- `DUI70!?EnsureVisible@Element@DirectUI@@QEAA_NXZ` at `0x18003c8c6`
- `DUI70!?EnsureVisible@Element@DirectUI@@QEAA_NXZ` at `0x18003c691`
- `DUI70!?EnsureVisible@Element@DirectUI@@QEAA_NXZ` at `0x18003c7d9`
- `DUI70!?EnsureVisible@Element@DirectUI@@QEAA_NXZ` at `0x18003c8c6`
- `DUI70!?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z` at `0x18003c6f0`
- `DUI70!?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z` at `0x18003c704`
- `DUI70!?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z` at `0x18003c6f0`
- `DUI70!?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z` at `0x18003c704`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18003c639`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18003c743`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18003c639`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18003c743`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18003c6a6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18003c819`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18003c6a6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18003c819`

## pseudocode

```c
__int64 __fastcall CLocalUserPage::OnNextButtonClicked(
        DisplayStatusHelper **this,
        enum TASKFLOW_TRAVERSAL_FLAGS *a2,
        unsigned __int16 **a3)
{
  struct DirectUI::Element *v6; // rdx
  struct DirectUI::Element *v7; // rdx
  struct DirectUI::Element *v8; // rdx
  int v9; // r14d
  DirectUI::Element *v10; // rcx
  const unsigned __int16 *ContentString; // rax
  unsigned int v12; // r8d
  __int64 v13; // rdx
  DirectUI::Value *Ptr; // rcx
  struct DirectUI::Element *v15; // rdx
  DisplayStatusHelper *v16; // rcx
  int v17; // edi
  DirectUI::Element *v18; // rsi
  const unsigned __int16 *v19; // rax
  DisplayStatusHelper *v20; // rcx
  const OLECHAR *v21; // r9
  int v22; // eax
  struct DirectUI::Element *v23; // rdx
  unsigned int v24; // r8d
  unsigned int v25; // eax
  DisplayStatusHelper *v26; // rcx
  DisplayStatusHelper *v27; // rcx
  __int64 v28; // rcx
  unsigned __int16 *v29; // rax
  __int64 v30; // rdx
  unsigned __int16 *v31; // rax
  DirectUI::Value *v32; // rcx
  int v33; // eax
  unsigned int v34; // r8d
  DirectUI::Element *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // r8
  unsigned int v40; // [rsp+30h] [rbp-D0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v41; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v42; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v43[526]; // [rsp+52h] [rbp-AEh] BYREF
  unsigned __int16 v44; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v45[526]; // [rsp+262h] [rbp+162h] BYREF

  *a3 = 0;
  DisplayStatusHelper::ClearStatus(this[9], a2);
  DisplayStatusHelper::ClearStatus(this[11], v6);
  DisplayStatusHelper::ClearStatus(this[15], v7);
  v9 = 0;
  if ( *((_DWORD *)this + 12) != 5 )
  {
    v10 = this[8];
    if ( (*((_BYTE *)v10 + 149) & 0x40) != 0 )
    {
      v41.Ptr = 0;
      v40 = 0;
      ContentString = DirectUI::Element::GetContentString(v10, (struct DirectUI::Value **)&v41);
      v9 = (*(__int64 (__fastcall **)(DisplayStatusHelper *, const unsigned __int16 *, unsigned int *))(*(_QWORD *)this[5] + 32LL))(
             this[5],
             ContentString,
             &v40);
      if ( v9 == -2147024809 )
      {
        v13 = v40;
        if ( v40 != 18 && v40 != 19 && v40 != 68 && v40 != 208 )
        {
          v13 = 3220;
          v40 = 3220;
        }
        DisplayStatusHelper::DisplayError(this[9], (struct DirectUI::Element *)v13, v12);
        DirectUI::Element::EnsureVisible(this[8]);
      }
      Ptr = (DirectUI::Value *)v41.Ptr;
      if ( v41.Ptr )
      {
        v41.Ptr = 0;
        DirectUI::Value::Release(Ptr);
      }
    }
    else
    {
      v9 = -2147024809;
      DisplayStatusHelper::DisplayRequired(this[9], v8);
    }
  }
  v42 = 0;
  memset_0(v43, 0, 0x200u);
  v44 = 0;
  memset_0(v45, 0, 0x200u);
  DirectUI::Element::GetEncodedContentString(this[10], &v42, 0x101u);
  DirectUI::Element::GetEncodedContentString(this[12], &v44, 0x101u);
  v16 = this[14];
  if ( !v42 || (*((_BYTE *)v16 + 149) & 0x40) != 0 )
  {
    v17 = 0;
    v18 = 0;
  }
  else
  {
    v17 = -2147024809;
    DisplayStatusHelper::DisplayRequired(this[15], v15);
    v18 = this[14];
    v16 = v18;
  }
  v41.Ptr = 0;
  v19 = DirectUI::Element::GetContentString(v16, (struct DirectUI::Value **)&v41);
  v20 = this[5];
  v40 = 0;
  v21 = &Class;
  if ( v19 )
    v21 = v19;
  v22 = (*(__int64 (__fastcall **)(DisplayStatusHelper *, unsigned __int16 *, unsigned __int16 *, const OLECHAR *, unsigned int *))(*(_QWORD *)v20 + 40LL))(
          v20,
          &v42,
          &v44,
          v21,
          &v40);
  if ( v22 < 0 )
  {
    v17 = v22;
    if ( v22 == -2147024809 )
    {
      v25 = v40;
      if ( (v40 & 1) != 0 )
      {
        v26 = this[11];
        v40 &= ~1u;
        DisplayStatusHelper::DisplayError(v26, (struct DirectUI::Element *)0xC97, v24);
        v25 = v40;
        v18 = this[10];
      }
      if ( (v25 & 2) != 0 )
      {
        v27 = this[15];
        v40 = v25 & 0xFFFFFFFD;
        DisplayStatusHelper::DisplayError(v27, v23);
        if ( v18 )
        {
LABEL_27:
          DirectUI::Element::EnsureVisible(v18);
          goto LABEL_28;
        }
        v18 = this[14];
      }
    }
  }
  if ( v18 )
    goto LABEL_27;
LABEL_28:
  v28 = 514;
  v29 = &v42;
  v30 = 514;
  do
  {
    *(_BYTE *)v29 = 0;
    v29 = (unsigned __int16 *)((char *)v29 + 1);
    --v30;
  }
  while ( v30 );
  v31 = &v44;
  do
  {
    *(_BYTE *)v31 = 0;
    v31 = (unsigned __int16 *)((char *)v31 + 1);
    --v28;
  }
  while ( v28 );
  v32 = (DirectUI::Value *)v41.Ptr;
  if ( v41.Ptr )
  {
    v41.Ptr = 0;
    DirectUI::Value::Release(v32);
  }
  if ( v17 >= 0 )
    v17 = v9;
  if ( v17 >= 0 )
  {
    v17 = CoAllocString(L"FinishPage", a3);
    if ( v17 >= 0 )
    {
      *(_DWORD *)a2 = 2;
      (*(void (__fastcall **)(DisplayStatusHelper *))(*(_QWORD *)this[5] + 48LL))(this[5]);
      v33 = (*(__int64 (__fastcall **)(DisplayStatusHelper *))(*(_QWORD *)this[5] + 80LL))(this[5]);
      v17 = v33;
      if ( v33 >= 0 )
        goto LABEL_46;
      if ( v33 == -2147023517 || v33 == -2147022672 )
      {
        DisplayStatusHelper::DisplayError(this[9], (struct DirectUI::Element *)0x44, v34);
        v35 = this[8];
      }
      else
      {
        if ( v33 != -2147022651 )
        {
          (*(void (__fastcall **)(DisplayStatusHelper *, _QWORD))(*(_QWORD *)this[5] + 88LL))(
            this[5],
            (unsigned int)v33);
          v17 = 0;
          goto LABEL_46;
        }
        DisplayStatusHelper::DisplayError(this[11], (struct DirectUI::Element *)0xF, v34);
        v35 = this[10];
      }
      DirectUI::Element::EnsureVisible(v35);
LABEL_46:
      v36 = *(_QWORD *)this[5];
      if ( v17 < 0 )
      {
        (*(void (**)(void))(v36 + 56))();
        CoTaskMemFree(*a3);
      }
      else
      {
        (*(void (**)(void))(v36 + 48))();
        if ( (Microsoft_Windows_User_ControlPanelEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(
            v37,
            (const EVENT_DESCRIPTOR *)UserAccount_Taskflow_LocalUserPage_OnNext,
            v38,
            1u,
            &v41);
      }
    }
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18003c5a0  mov     [rsp-8+arg_18], rbx
0x18003c5a5  push    rbp
0x18003c5a6  push    rsi
0x18003c5a7  push    rdi
0x18003c5a8  push    r12
0x18003c5aa  push    r13
0x18003c5ac  push    r14
0x18003c5ae  push    r15
0x18003c5b0  lea     rbp, [rsp-380h]
0x18003c5b8  sub     rsp, 480h
0x18003c5bf  mov     rax, cs:__security_cookie
0x18003c5c6  xor     rax, rsp
0x18003c5c9  mov     [rbp+3B0h+var_40], rax
0x18003c5d0  mov     rbx, rcx
0x18003c5d3  xor     r13d, r13d
0x18003c5d6  mov     [r8], r13
0x18003c5d9  mov     r15, r8
0x18003c5dc  mov     rcx, [rcx+48h]; this
0x18003c5e0  mov     r12, rdx
0x18003c5e3  call    ?ClearStatus@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@@Z; DisplayStatusHelper::ClearStatus(DirectUI::Element *)
0x18003c5e8  mov     rcx, [rbx+58h]; this
0x18003c5ec  call    ?ClearStatus@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@@Z; DisplayStatusHelper::ClearStatus(DirectUI::Element *)
0x18003c5f1  mov     rcx, [rbx+78h]; this
0x18003c5f5  call    ?ClearStatus@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@@Z; DisplayStatusHelper::ClearStatus(DirectUI::Element *)
0x18003c5fa  cmp     dword ptr [rbx+30h], 5
0x18003c5fe  mov     r14d, r13d
0x18003c601  mov     esi, 80070057h
0x18003c606  jz      loc_18003C6AC
0x18003c60c  mov     rcx, [rbx+40h]
0x18003c610  test    byte ptr [rcx+95h], 40h
0x18003c617  jnz     short loc_18003C62A
0x18003c619  mov     rcx, [rbx+48h]; this
0x18003c61d  mov     r14d, esi
0x18003c620  call    ?DisplayRequired@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@@Z; DisplayStatusHelper::DisplayRequired(DirectUI::Element *)
0x18003c625  jmp     loc_18003C6AC
0x18003c62a  lea     rdx, [rsp+4B0h+var_478]
0x18003c62f  mov     [rsp+4B0h+var_478], r13
0x18003c634  mov     [rsp+4B0h+var_480], r13d
0x18003c639  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x18003c63f  mov     rcx, [rbx+28h]
0x18003c643  lea     r8, [rsp+4B0h+var_480]
0x18003c648  mov     rdx, rax
0x18003c64b  mov     rax, [rcx]
0x18003c64e  mov     rax, [rax+20h]
0x18003c652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c657  mov     r14d, eax
0x18003c65a  cmp     eax, esi
0x18003c65c  jnz     short loc_18003C697
0x18003c65e  mov     edx, [rsp+4B0h+var_480]
0x18003c662  mov     ecx, edx
0x18003c664  sub     ecx, 12h
0x18003c667  jz      short loc_18003C684
0x18003c669  sub     ecx, 1
0x18003c66c  jz      short loc_18003C684
0x18003c66e  sub     ecx, 31h ; '1'
0x18003c671  jz      short loc_18003C684
0x18003c673  cmp     ecx, 8Ch
0x18003c679  jz      short loc_18003C684
0x18003c67b  mov     edx, 0C94h; struct DirectUI::Element *
0x18003c680  mov     [rsp+4B0h+var_480], edx
0x18003c684  mov     rcx, [rbx+48h]; this
0x18003c688  call    ?DisplayError@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@I@Z; DisplayStatusHelper::DisplayError(DirectUI::Element *,uint)
0x18003c68d  mov     rcx, [rbx+40h]
0x18003c691  call    cs:__imp_?EnsureVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::EnsureVisible(void)
0x18003c697  mov     rcx, [rsp+4B0h+var_478]
0x18003c69c  test    rcx, rcx
0x18003c69f  jz      short loc_18003C6AC
0x18003c6a1  mov     [rsp+4B0h+var_478], r13
0x18003c6a6  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18003c6ac  mov     edi, 200h
0x18003c6b1  mov     [rsp+4B0h+var_460], r13w
0x18003c6b7  mov     r8d, edi; Size
0x18003c6ba  lea     rcx, [rsp+4B0h+var_45E]; void *
0x18003c6bf  xor     edx, edx; Val
0x18003c6c1  call    memset_0
0x18003c6c6  mov     r8d, edi; Size
0x18003c6c9  mov     [rbp+3B0h+var_250], r13w
0x18003c6d1  xor     edx, edx; Val
0x18003c6d3  lea     rcx, [rbp+3B0h+var_24E]; void *
0x18003c6da  call    memset_0
0x18003c6df  mov     rcx, [rbx+50h]
0x18003c6e3  lea     rdx, [rsp+4B0h+var_460]
0x18003c6e8  mov     edi, 101h
0x18003c6ed  mov     r8d, edi
0x18003c6f0  call    cs:__imp_?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z; DirectUI::Element::GetEncodedContentString(ushort *,unsigned __int64)
0x18003c6f6  mov     rcx, [rbx+60h]
0x18003c6fa  lea     rdx, [rbp+3B0h+var_250]
0x18003c701  mov     r8d, edi
0x18003c704  call    cs:__imp_?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z; DirectUI::Element::GetEncodedContentString(ushort *,unsigned __int64)
0x18003c70a  mov     rcx, [rbx+70h]
0x18003c70e  cmp     [rsp+4B0h+var_460], r13w
0x18003c714  jz      short loc_18003C733
0x18003c716  test    byte ptr [rcx+95h], 40h
0x18003c71d  jnz     short loc_18003C733
0x18003c71f  mov     rcx, [rbx+78h]; this
0x18003c723  mov     edi, esi
0x18003c725  call    ?DisplayRequired@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@@Z; DisplayStatusHelper::DisplayRequired(DirectUI::Element *)
0x18003c72a  mov     rsi, [rbx+70h]
0x18003c72e  mov     rcx, rsi
0x18003c731  jmp     short loc_18003C739
0x18003c733  mov     edi, r13d
0x18003c736  mov     rsi, r13
0x18003c739  lea     rdx, [rsp+4B0h+var_478]
0x18003c73e  mov     [rsp+4B0h+var_478], r13
0x18003c743  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x18003c749  mov     rcx, [rbx+28h]
0x18003c74d  lea     rdx, [rsp+4B0h+var_480]
0x18003c752  test    rax, rax
0x18003c755  mov     [rsp+4B0h+var_480], r13d
0x18003c75a  mov     [rsp+4B0h+var_490], rdx
0x18003c75f  lea     r9, Class
0x18003c766  cmovnz  r9, rax
0x18003c76a  lea     r8, [rbp+3B0h+var_250]
0x18003c771  mov     rax, [rcx]
0x18003c774  lea     rdx, [rsp+4B0h+var_460]
0x18003c779  mov     rax, [rax+28h]
0x18003c77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c782  test    eax, eax
0x18003c784  jns     short loc_18003C7D1
0x18003c786  mov     edi, eax
0x18003c788  cmp     eax, 80070057h
0x18003c78d  jnz     short loc_18003C7D1
0x18003c78f  mov     eax, [rsp+4B0h+var_480]
0x18003c793  test    al, 1
0x18003c795  jz      short loc_18003C7B4
0x18003c797  mov     rcx, [rbx+58h]; this
0x18003c79b  and     eax, 0FFFFFFFEh
0x18003c79e  mov     edx, 0C97h; struct DirectUI::Element *
0x18003c7a3  mov     [rsp+4B0h+var_480], eax
0x18003c7a7  call    ?DisplayError@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@I@Z; DisplayStatusHelper::DisplayError(DirectUI::Element *,uint)
0x18003c7ac  mov     eax, [rsp+4B0h+var_480]
0x18003c7b0  mov     rsi, [rbx+50h]
0x18003c7b4  test    al, 2
0x18003c7b6  jz      short loc_18003C7D1
0x18003c7b8  mov     rcx, [rbx+78h]; this
0x18003c7bc  and     eax, 0FFFFFFFDh
0x18003c7bf  mov     [rsp+4B0h+var_480], eax
0x18003c7c3  call    ?DisplayError@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@@Z; DisplayStatusHelper::DisplayError(DirectUI::Element *)
0x18003c7c8  test    rsi, rsi
0x18003c7cb  jnz     short loc_18003C7D6
0x18003c7cd  mov     rsi, [rbx+70h]
0x18003c7d1  test    rsi, rsi
0x18003c7d4  jz      short loc_18003C7DF
0x18003c7d6  mov     rcx, rsi
0x18003c7d9  call    cs:__imp_?EnsureVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::EnsureVisible(void)
0x18003c7df  mov     ecx, 202h
0x18003c7e4  lea     rax, [rsp+4B0h+var_460]
0x18003c7e9  mov     edx, ecx
0x18003c7eb  mov     [rax], r13b
0x18003c7ee  inc     rax
0x18003c7f1  sub     rdx, 1
0x18003c7f5  jnz     short loc_18003C7EB
0x18003c7f7  lea     rax, [rbp+3B0h+var_250]
0x18003c7fe  mov     [rax], r13b
0x18003c801  inc     rax
0x18003c804  sub     rcx, 1
0x18003c808  jnz     short loc_18003C7FE
0x18003c80a  mov     rcx, [rsp+4B0h+var_478]
0x18003c80f  test    rcx, rcx
0x18003c812  jz      short loc_18003C81F
0x18003c814  mov     [rsp+4B0h+var_478], r13
0x18003c819  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18003c81f  test    edi, edi
0x18003c821  cmovns  edi, r14d
0x18003c825  test    edi, edi
0x18003c827  js      loc_18003C919
0x18003c82d  mov     rdx, r15; unsigned __int16 **
0x18003c830  lea     rcx, aFinishpage; "FinishPage"
0x18003c837  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18003c83c  mov     edi, eax
0x18003c83e  test    eax, eax
0x18003c840  js      loc_18003C919
0x18003c846  mov     dword ptr [r12], 2
0x18003c84e  mov     rcx, [rbx+28h]
0x18003c852  mov     rax, [rcx]
0x18003c855  mov     rax, [rax+30h]
0x18003c859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c85e  mov     rcx, [rbx+28h]
0x18003c862  mov     rax, [rcx]
0x18003c865  mov     rax, [rax+50h]
0x18003c869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c86e  mov     edi, eax
0x18003c870  test    eax, eax
0x18003c872  jns     short loc_18003C8CC
0x18003c874  cmp     eax, 80070563h
0x18003c879  jz      short loc_18003C8B4
0x18003c87b  cmp     eax, 800708B0h
0x18003c880  jz      short loc_18003C8B4
0x18003c882  cmp     eax, 800708C5h
0x18003c887  jnz     short loc_18003C89D
0x18003c889  mov     rcx, [rbx+58h]; this
0x18003c88d  mov     edx, 0Fh; struct DirectUI::Element *
0x18003c892  call    ?DisplayError@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@I@Z; DisplayStatusHelper::DisplayError(DirectUI::Element *,uint)
0x18003c897  mov     rcx, [rbx+50h]
0x18003c89b  jmp     short loc_18003C8C6
0x18003c89d  mov     rcx, [rbx+28h]
0x18003c8a1  mov     edx, edi
0x18003c8a3  mov     rax, [rcx]
0x18003c8a6  mov     rax, [rax+58h]
0x18003c8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8af  mov     edi, r13d
0x18003c8b2  jmp     short loc_18003C8CC
0x18003c8b4  mov     rcx, [rbx+48h]; this
0x18003c8b8  mov     edx, 44h ; 'D'; struct DirectUI::Element *
0x18003c8bd  call    ?DisplayError@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@I@Z; DisplayStatusHelper::DisplayError(DirectUI::Element *,uint)
0x18003c8c2  mov     rcx, [rbx+40h]
0x18003c8c6  call    cs:__imp_?EnsureVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::EnsureVisible(void)
0x18003c8cc  mov     rcx, [rbx+28h]
0x18003c8d0  mov     rax, [rcx]
0x18003c8d3  test    edi, edi
0x18003c8d5  js      short loc_18003C907
0x18003c8d7  mov     rax, [rax+30h]
0x18003c8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8e0  test    cs:Microsoft_Windows_User_ControlPanelEnableBits, 2
0x18003c8e7  jz      short loc_18003C919
0x18003c8e9  lea     rax, [rsp+4B0h+var_478]
0x18003c8ee  mov     r9d, 1
0x18003c8f4  lea     rdx, UserAccount_Taskflow_LocalUserPage_OnNext
0x18003c8fb  mov     [rsp+4B0h+var_490], rax
0x18003c900  call    McGenEventWrite_EventWriteTransfer
0x18003c905  jmp     short loc_18003C919
0x18003c907  mov     rax, [rax+38h]
0x18003c90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c910  mov     rcx, [r15]; pv
0x18003c913  call    cs:__imp_CoTaskMemFree
0x18003c919  mov     eax, edi
0x18003c91b  mov     rcx, [rbp+3B0h+var_40]
0x18003c922  xor     rcx, rsp; StackCookie
0x18003c925  call    __security_check_cookie
0x18003c92a  mov     rbx, [rsp+4B0h+arg_18]
0x18003c932  add     rsp, 480h
0x18003c939  pop     r15
0x18003c93b  pop     r14
0x18003c93d  pop     r13
0x18003c93f  pop     r12
0x18003c941  pop     rdi
0x18003c942  pop     rsi
0x18003c943  pop     rbp
0x18003c944  retn
```
