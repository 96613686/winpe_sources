# EmailOperationContext::SendMessageW(int,UdmItemUpdate const *,UdmOperationResult *)

- ea: `0x1800b4b24`
- end: `0x1800b500f`
- name: `?SendMessageW@EmailOperationContext@@QEAAJHPEBUUdmItemUpdate@@PEAUUdmOperationResult@@@Z`
- size: `1259`
- prototype: `__int64 __fastcall(EmailOperationContext *__hidden this, struct IMessage *, const struct UdmItemUpdate *, struct UdmOperationResult *)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800b3f98`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18000dfe0`
- `0x180022fa8`
- `0x180032228`
- `0x18003848c`
- `0x18003863c`
- `0x18006c7ec`
- `0x18006fc80`
- `0x180071608`
- `0x180075f98`
- `0x18007ba18`
- `0x18007d2d0`
- `0x1800836ac`
- `0x1800b0ae4`
- `0x1800b47a0`
- `0x1800b4b24`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `CEMAPI!MAPIFreeBuffer` at `0x1800b4db7`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b4f78`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b4fb8`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b4fc8`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b4db7`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b4f78`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b4fb8`
- `CEMAPI!MAPIFreeBuffer` at `0x1800b4fc8`
- `unistore!CreateStoreManager` at `0x1800b4be4`
- `unistore!CreateStoreManager` at `0x1800b4be4`
- `UserDataTypeHelperUtil!MapiIdToEmailUdmId` at `0x1800b4f94`
- `UserDataTypeHelperUtil!MapiIdToEmailUdmId` at `0x1800b4f94`

## string_xrefs

- `0x1800b4b6c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b4bf6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b4c32`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b4c74`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`

## pseudocode

```c
__int64 __fastcall EmailOperationContext::SendMessageW(
        EmailOperationContext *this,
        struct IMessage *a2,
        const struct UdmItemUpdate *a3,
        struct UdmOperationResult *a4)
{
  unsigned int v6; // r13d
  __int64 v8; // r9
  unsigned int VerbExecutedOnBaseMessage; // ebx
  __int64 v10; // rdx
  __int64 v11; // rax
  unsigned int *v12; // rsi
  int v13; // eax
  int v14; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // xmm0_8
  int v20; // eax
  int v21; // eax
  unsigned int *v22; // r8
  __int64 v23; // r9
  struct IUnknown *v24; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  void **v26; // rax
  int v27; // eax
  __int64 v28; // r9
  __int64 v29; // rcx
  int v30; // ecx
  unsigned int v31; // ecx
  int v32; // ecx
  __int128 *v33; // rcx
  unsigned int v34; // ecx
  int v35; // r8d
  struct IMessage *v36; // r8
  __int64 v37; // rax
  __int128 v38; // xmm0
  __int64 v39; // r10
  int SpecialFolderId; // eax
  __int64 v41; // r9
  void *v42; // rcx
  int v43; // eax
  struct IUnknown *v45; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v47; // [rsp+40h] [rbp-C0h] BYREF
  int v48; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID v49; // [rsp+48h] [rbp-B8h] BYREF
  int v50; // [rsp+50h] [rbp-B0h] BYREF
  struct IUSStoreManager *v51; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v52; // [rsp+60h] [rbp-A0h] BYREF
  int v53; // [rsp+70h] [rbp-90h]
  _BYTE v54[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v55[24]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-30h] BYREF
  int v57; // [rsp+D8h] [rbp-28h]
  __int128 v58; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v59; // [rsp+F0h] [rbp-10h]
  _DWORD v60[6]; // [rsp+F8h] [rbp-8h] BYREF
  int v61; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v62[4]; // [rsp+114h] [rbp+14h] BYREF
  int v63; // [rsp+118h] [rbp+18h]
  int v64; // [rsp+128h] [rbp+28h]
  unsigned int v65; // [rsp+130h] [rbp+30h]
  int v66; // [rsp+140h] [rbp+40h]
  __int64 v67; // [rsp+148h] [rbp+48h]
  unsigned int v68; // [rsp+158h] [rbp+58h]
  int v69; // [rsp+160h] [rbp+60h]
  __int128 *v70; // [rsp+168h] [rbp+68h]

  v6 = (unsigned int)a2;
  if ( a3 )
  {
    v11 = *(_QWORD *)this;
    v12 = (unsigned int *)((char *)a3 + 4);
    v48 = 0;
    *(_QWORD *)&v52 = (char *)a3 + 4;
    VerbExecutedOnBaseMessage = (*(__int64 (__fastcall **)(EmailOperationContext *, char *, _QWORD, int *))(v11 + 24))(
                                  this,
                                  (char *)a3 + 4,
                                  0,
                                  &v48);
    if ( (VerbExecutedOnBaseMessage & 0x80000000) != 0 )
    {
      v8 = 361;
      v10 = 1;
      goto LABEL_4;
    }
    if ( v48 < 1 )
    {
      v8 = 362;
      VerbExecutedOnBaseMessage = -2147024891;
      goto LABEL_3;
    }
    v51 = 0;
    v13 = CreateStoreManager(0, &v51);
    VerbExecutedOnBaseMessage = v13;
    if ( v13 < 0 )
    {
      Log_HREvent(
        (unsigned int)v13,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        365);
LABEL_63:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v51);
      return VerbExecutedOnBaseMessage;
    }
    AutoTopLevelTransaction::AutoTopLevelTransaction((AutoTopLevelTransaction *)v54);
    v14 = AutoTopLevelTransaction::Begin((AutoTopLevelTransaction *)v54, v51, *v12);
    VerbExecutedOnBaseMessage = v14;
    if ( v14 < 0 )
    {
      v15 = 368;
LABEL_13:
      v16 = 1;
      v17 = (unsigned int)v14;
LABEL_14:
      Log_HREvent(
        v17,
        v16,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        v15);
LABEL_15:
      AutoTopLevelTransaction::~AutoTopLevelTransaction((AutoTopLevelTransaction *)v54);
      goto LABEL_63;
    }
    v14 = EmailOperationContext::SaveDraft(this, a3, 0, a4);
    VerbExecutedOnBaseMessage = v14;
    if ( v14 < 0 )
    {
      v15 = 372;
      goto LABEL_13;
    }
    if ( *(_DWORD *)a4 != 4 )
      Log_AssertionEvent_2(
        v18,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        373);
    if ( v6 && !*((_DWORD *)a4 + 18) )
    {
      VerbExecutedOnBaseMessage = -2147024846;
      v15 = 378;
      v17 = 2147942450LL;
      v16 = 0;
      goto LABEL_14;
    }
    if ( *((_DWORD *)a3 + 5) == 8 )
    {
      v19 = *((_QWORD *)a3 + 2);
      v20 = *((_DWORD *)a3 + 6);
    }
    else
    {
      v19 = *((_QWORD *)a4 + 1);
      v20 = *((_DWORD *)a4 + 4);
    }
    v57 = v20;
    v45 = 0;
    v56 = v19;
    v21 = EmailOperationContext::MapiOpenItemById(this, (const struct UdmObjectId *)&v56, 0, &v45, 0);
    VerbExecutedOnBaseMessage = v21;
    if ( v21 < 0 )
    {
      v23 = 395;
LABEL_28:
      Log_HREvent(
        (unsigned int)v21,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        v23);
LABEL_29:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v45);
      goto LABEL_15;
    }
    v47 = 0;
    v21 = EmailHelper::MapNamedPropTag((EmailHelper *)1, (unsigned int)&v47, v22);
    VerbExecutedOnBaseMessage = v21;
    if ( v21 < 0 )
    {
      v23 = 398;
      goto LABEL_28;
    }
    v50 = 0;
    pv = 0;
    v24 = v45;
    v60[0] = 3;
    v60[1] = 236388355;
    v60[2] = 235339779;
    v60[3] = v47;
    Release = v45->lpVtbl[1].Release;
    v26 = tlx::replace<_SPropValue,&void FreeSPropValueArray(_SPropValue *)>(&pv);
    v27 = ((__int64 (__fastcall *)(struct IUnknown *, _DWORD *, __int64, int *, void **))Release)(
            v24,
            v60,
            0x80000000LL,
            &v50,
            v26);
    VerbExecutedOnBaseMessage = v27;
    if ( v27 >= 0 )
    {
      memset_0(v62, 0, 0x5Cu);
      v61 = 236388355;
      v30 = *((_DWORD *)pv + 2) | 0x20000;
      v64 = 235339779;
      v63 = v30;
      v31 = *((_DWORD *)pv + 8) & 0xFFFFFFF7;
      v66 = 930611220;
      v65 = v31;
      v32 = 0;
      v59 = 0;
      v67 = 0;
      v58 = 0;
      if ( *((_DWORD *)pv + 12) == v47 && *((_DWORD *)pv + 14) == 20 )
      {
        v33 = (__int128 *)*((_QWORD *)pv + 8);
        v58 = *v33;
        v32 = *((_DWORD *)v33 + 4);
      }
      if ( v6 )
        v34 = v32 | 0x10000;
      else
        v34 = v32 & 0xFFFEFFFF;
      v59 = v34;
      v68 = v47;
      v70 = &v58;
      v69 = 20;
      v27 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, int *))v45->lpVtbl[2].Release)(v45, 4, &v61);
      VerbExecutedOnBaseMessage = v27;
      if ( v27 >= 0 )
      {
        v27 = EmailHelper::EncodeBodyForSend((EmailHelper *)v45, (struct IMessage *)v6, v35);
        VerbExecutedOnBaseMessage = v27;
        if ( v27 >= 0 )
        {
          v27 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v45->lpVtbl[6].Release)(v45, 0);
          VerbExecutedOnBaseMessage = v27;
          if ( v27 >= 0 )
          {
            VerbExecutedOnBaseMessage = EmailHelper::SetLastVerbExecutedOnBaseMessage(
                                          this,
                                          (struct EmailOperationContext *)v45,
                                          v36);
            if ( !(unsigned int)IsItemNotFoundError(VerbExecutedOnBaseMessage) && (int)v29 < 0 )
            {
              v28 = 453;
              goto LABEL_35;
            }
            v27 = AutoTopLevelTransaction::End((AutoTopLevelTransaction *)v54, 1);
            VerbExecutedOnBaseMessage = v27;
            if ( v27 >= 0 )
            {
              v49 = 0;
              tlx::replace<_SPropValue,&void FreeSPropValueArray(_SPropValue *)>(&v49);
              v37 = UdmIdToMapiStoreId(v55, v52);
              v38 = *(_OWORD *)v37;
              v53 = *(_DWORD *)(v37 + 16);
              v52 = v38;
              SpecialFolderId = EmailOperationContext::GetSpecialFolderId(this, &v52, 3, v39, 0);
              VerbExecutedOnBaseMessage = SpecialFolderId;
              if ( SpecialFolderId >= 0 )
              {
                MapiIdToEmailUdmId(&v52, *((unsigned int *)v49 + 2), *((_QWORD *)v49 + 2), v41);
                v42 = v49;
                v43 = DWORD2(v52);
                *((_QWORD *)a4 + 4) = v52;
                *((_DWORD *)a4 + 10) = v43;
                if ( v42 )
                  MAPIFreeBuffer(v42);
                if ( pv )
                  MAPIFreeBuffer(pv);
                ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v45);
                AutoTopLevelTransaction::~AutoTopLevelTransaction((AutoTopLevelTransaction *)v54);
                VerbExecutedOnBaseMessage = 0;
                goto LABEL_63;
              }
              Log_HREvent(
                (unsigned int)SpecialFolderId,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
                465);
              if ( v49 )
                MAPIFreeBuffer(v49);
              goto LABEL_36;
            }
            v28 = 457;
          }
          else
          {
            v28 = 447;
          }
        }
        else
        {
          v28 = 444;
        }
      }
      else
      {
        v28 = 442;
      }
    }
    else
    {
      v28 = 405;
    }
    v29 = (unsigned int)v27;
LABEL_35:
    Log_HREvent(
      v29,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
      v28);
LABEL_36:
    if ( pv )
      MAPIFreeBuffer(pv);
    goto LABEL_29;
  }
  v8 = 358;
  VerbExecutedOnBaseMessage = -2147024809;
LABEL_3:
  v10 = 0;
LABEL_4:
  Log_HREvent(
    VerbExecutedOnBaseMessage,
    v10,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
    v8);
  return VerbExecutedOnBaseMessage;
}

```

## disassembly

```asm
0x1800b4b24  push    rbp
0x1800b4b26  push    rbx
0x1800b4b27  push    rsi
0x1800b4b28  push    rdi
0x1800b4b29  push    r12
0x1800b4b2b  push    r13
0x1800b4b2d  push    r14
0x1800b4b2f  push    r15
0x1800b4b31  lea     rbp, [rsp-88h]
0x1800b4b39  sub     rsp, 188h
0x1800b4b40  mov     rax, cs:__security_cookie
0x1800b4b47  xor     rax, rsp
0x1800b4b4a  mov     [rbp+0C0h+var_50], rax
0x1800b4b4e  mov     r15, r9
0x1800b4b51  mov     rdi, r8
0x1800b4b54  mov     r13d, edx
0x1800b4b57  mov     r12, rcx
0x1800b4b5a  test    r8, r8
0x1800b4b5d  jnz     short loc_1800B4B7F
0x1800b4b5f  mov     r9d, 166h
0x1800b4b65  mov     ebx, 80070057h
0x1800b4b6a  xor     edx, edx
0x1800b4b6c  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b4b73  mov     ecx, ebx
0x1800b4b75  call    Log_HREvent
0x1800b4b7a  jmp     loc_1800B4FED
0x1800b4b7f  mov     rax, [rcx]
0x1800b4b82  lea     rsi, [r8+4]
0x1800b4b86  lea     r9, [rsp+1C0h+var_17C]
0x1800b4b8b  mov     [rsp+1C0h+var_17C], 0
0x1800b4b93  xor     r8d, r8d
0x1800b4b96  mov     qword ptr [rsp+1C0h+var_160], rsi
0x1800b4b9b  mov     rdx, rsi
0x1800b4b9e  mov     rax, [rax+18h]
0x1800b4ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ba7  mov     ebx, eax
0x1800b4ba9  test    eax, eax
0x1800b4bab  jns     short loc_1800B4BBA
0x1800b4bad  mov     r9d, 169h
0x1800b4bb3  mov     edx, 1
0x1800b4bb8  jmp     short loc_1800B4B6C
0x1800b4bba  mov     r14d, 1
0x1800b4bc0  cmp     [rsp+1C0h+var_17C], r14d
0x1800b4bc5  jge     short loc_1800B4BD4
0x1800b4bc7  mov     r9d, 16Ah
0x1800b4bcd  mov     ebx, 80070005h
0x1800b4bd2  jmp     short loc_1800B4B6A
0x1800b4bd4  lea     rdx, [rsp+1C0h+var_168]
0x1800b4bd9  mov     [rsp+1C0h+var_168], 0
0x1800b4be2  xor     ecx, ecx
0x1800b4be4  call    cs:__imp_CreateStoreManager
0x1800b4bea  mov     ebx, eax
0x1800b4bec  test    eax, eax
0x1800b4bee  jns     short loc_1800B4C0C
0x1800b4bf0  mov     r9d, 16Dh
0x1800b4bf6  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b4bfd  mov     edx, r14d
0x1800b4c00  mov     ecx, eax
0x1800b4c02  call    Log_HREvent
0x1800b4c07  jmp     loc_1800B4FE3
0x1800b4c0c  lea     rcx, [rbp+0C0h+var_140]; this
0x1800b4c10  call    ??0AutoTopLevelTransaction@@QEAA@XZ; AutoTopLevelTransaction::AutoTopLevelTransaction(void)
0x1800b4c15  mov     r8d, [rsi]; unsigned int
0x1800b4c18  lea     rcx, [rbp+0C0h+var_140]; this
0x1800b4c1c  mov     rdx, [rsp+1C0h+var_168]; struct IUSStoreManager *
0x1800b4c21  call    ?Begin@AutoTopLevelTransaction@@QEAAJPEAUIUSStoreManager@@K@Z; AutoTopLevelTransaction::Begin(IUSStoreManager *,ulong)
0x1800b4c26  mov     ebx, eax
0x1800b4c28  test    eax, eax
0x1800b4c2a  jns     short loc_1800B4C51
0x1800b4c2c  mov     r9d, 170h
0x1800b4c32  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b4c39  mov     edx, r14d
0x1800b4c3c  mov     ecx, eax
0x1800b4c3e  call    Log_HREvent
0x1800b4c43  lea     rcx, [rbp+0C0h+var_140]; this
0x1800b4c47  call    ??1AutoTopLevelTransaction@@UEAA@XZ; AutoTopLevelTransaction::~AutoTopLevelTransaction(void)
0x1800b4c4c  jmp     loc_1800B4FE3
0x1800b4c51  mov     r9, r15; struct UdmOperationResult *
0x1800b4c54  xor     r8d, r8d; int
0x1800b4c57  mov     rdx, rdi; struct UdmItemUpdate *
0x1800b4c5a  mov     rcx, r12; this
0x1800b4c5d  call    ?SaveDraft@EmailOperationContext@@AEAAJPEBUUdmItemUpdate@@HPEAUUdmOperationResult@@@Z; EmailOperationContext::SaveDraft(UdmItemUpdate const *,int,UdmOperationResult *)
0x1800b4c62  mov     ebx, eax
0x1800b4c64  test    eax, eax
0x1800b4c66  jns     short loc_1800B4C70
0x1800b4c68  mov     r9d, 174h
0x1800b4c6e  jmp     short loc_1800B4C32
0x1800b4c70  cmp     dword ptr [r15], 4
0x1800b4c74  lea     rsi, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b4c7b  jz      short loc_1800B4C8B
0x1800b4c7d  mov     r8d, 175h
0x1800b4c83  mov     rdx, rsi
0x1800b4c86  call    Log_AssertionEvent_2
0x1800b4c8b  test    r13d, r13d
0x1800b4c8e  jz      short loc_1800B4CAB
0x1800b4c90  cmp     dword ptr [r15+48h], 0
0x1800b4c95  jnz     short loc_1800B4CAB
0x1800b4c97  mov     ebx, 80070032h
0x1800b4c9c  mov     r9d, 17Ah
0x1800b4ca2  mov     ecx, ebx
0x1800b4ca4  mov     r8, rsi
0x1800b4ca7  xor     edx, edx
0x1800b4ca9  jmp     short loc_1800B4C3E
0x1800b4cab  cmp     dword ptr [rdi+14h], 8
0x1800b4caf  jnz     short loc_1800B4CBB
0x1800b4cb1  movsd   xmm0, qword ptr [rdi+10h]
0x1800b4cb6  mov     eax, [rdi+18h]
0x1800b4cb9  jmp     short loc_1800B4CC5
0x1800b4cbb  movsd   xmm0, qword ptr [r15+8]
0x1800b4cc1  mov     eax, [r15+10h]
0x1800b4cc5  xor     edi, edi
0x1800b4cc7  mov     [rbp+0C0h+var_E8], eax
0x1800b4cca  lea     r9, [rsp+1C0h+var_190]; struct IUnknown **
0x1800b4ccf  mov     [rsp+1C0h+var_190], rdi
0x1800b4cd4  xor     r8d, r8d; int
0x1800b4cd7  mov     [rsp+1C0h+var_1A0], rdi; struct IMsgStore **
0x1800b4cdc  lea     rdx, [rbp+0C0h+var_F0]; struct UdmObjectId *
0x1800b4ce0  movsd   [rbp+0C0h+var_F0], xmm0
0x1800b4ce5  mov     rcx, r12; this
0x1800b4ce8  call    ?MapiOpenItemById@EmailOperationContext@@QEAAJAEBUUdmObjectId@@HPEAPEAUIUnknown@@PEAPEAUIMsgStore@@@Z; EmailOperationContext::MapiOpenItemById(UdmObjectId const &,int,IUnknown * *,IMsgStore * *)
0x1800b4ced  mov     ebx, eax
0x1800b4cef  test    eax, eax
0x1800b4cf1  jns     short loc_1800B4D15
0x1800b4cf3  mov     r9d, 18Bh
0x1800b4cf9  mov     r8, rsi
0x1800b4cfc  mov     edx, r14d
0x1800b4cff  mov     ecx, eax
0x1800b4d01  call    Log_HREvent
0x1800b4d06  lea     rcx, [rsp+1C0h+var_190]
0x1800b4d0b  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800b4d10  jmp     loc_1800B4C43
0x1800b4d15  lea     rdx, [rsp+1C0h+var_180]; unsigned int
0x1800b4d1a  mov     [rsp+1C0h+var_180], edi
0x1800b4d1e  mov     ecx, r14d; this
0x1800b4d21  call    ?MapNamedPropTag@EmailHelper@@YAJKPEAK@Z; EmailHelper::MapNamedPropTag(ulong,ulong *)
0x1800b4d26  mov     ebx, eax
0x1800b4d28  test    eax, eax
0x1800b4d2a  jns     short loc_1800B4D34
0x1800b4d2c  mov     r9d, 18Eh
0x1800b4d32  jmp     short loc_1800B4CF9
0x1800b4d34  mov     eax, [rsp+1C0h+var_180]
0x1800b4d38  lea     rcx, [rsp+1C0h+pv]
0x1800b4d3d  mov     [rsp+1C0h+var_170], edi
0x1800b4d41  mov     [rsp+1C0h+pv], rdi
0x1800b4d46  mov     rdi, [rsp+1C0h+var_190]
0x1800b4d4b  mov     [rbp+0C0h+var_C8], 3
0x1800b4d52  mov     [rbp+0C0h+var_C4], 0E170003h
0x1800b4d59  mov     [rbp+0C0h+var_C0], 0E070003h
0x1800b4d60  mov     [rbp+0C0h+var_BC], eax
0x1800b4d63  mov     rax, [rdi]
0x1800b4d66  mov     rbx, [rax+28h]
0x1800b4d6a  call    ??$replace@U_SPropValue@@$1?FreeSPropValueArray@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_SPropValue@@AEAV?$auto_array_ptr@U_SPropValue@@$1?FreeSPropValueArray@@YAXPEAU1@@Z@0@@Z; tlx::replace<_SPropValue,&FreeSPropValueArray(_SPropValue *)>(tlx::auto_array_ptr<_SPropValue,&FreeSPropValueArray(_SPropValue *)> &)
0x1800b4d6f  mov     [rsp+1C0h+var_1A0], rax
0x1800b4d74  lea     r9, [rsp+1C0h+var_170]
0x1800b4d79  mov     rax, rbx
0x1800b4d7c  lea     rdx, [rbp+0C0h+var_C8]
0x1800b4d80  mov     r8d, 80000000h
0x1800b4d86  mov     rcx, rdi
0x1800b4d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d8e  xor     edi, edi
0x1800b4d90  mov     ebx, eax
0x1800b4d92  test    eax, eax
0x1800b4d94  jns     short loc_1800B4DC2
0x1800b4d96  mov     r9d, 195h
0x1800b4d9c  mov     ecx, eax
0x1800b4d9e  mov     edx, r14d
0x1800b4da1  mov     r8, rsi
0x1800b4da4  call    Log_HREvent
0x1800b4da9  mov     rcx, [rsp+1C0h+pv]; pv
0x1800b4dae  test    rcx, rcx
0x1800b4db1  jz      loc_1800B4D06
0x1800b4db7  call    cs:__imp_MAPIFreeBuffer
0x1800b4dbd  jmp     loc_1800B4D06
0x1800b4dc2  xor     edx, edx; Val
0x1800b4dc4  lea     rcx, [rbp+0C0h+var_AC]; void *
0x1800b4dc8  lea     r8d, [rdx+5Ch]; Size
0x1800b4dcc  call    memset_0
0x1800b4dd1  mov     rax, [rsp+1C0h+pv]
0x1800b4dd6  xorps   xmm0, xmm0
0x1800b4dd9  mov     edx, [rsp+1C0h+var_180]
0x1800b4ddd  mov     [rbp+0C0h+var_B0], 0E170003h
0x1800b4de4  mov     ecx, [rax+8]
0x1800b4de7  bts     ecx, 11h
0x1800b4deb  mov     [rbp+0C0h+var_98], 0E070003h
0x1800b4df2  mov     [rbp+0C0h+var_A8], ecx
0x1800b4df5  mov     ecx, [rax+20h]
0x1800b4df8  and     ecx, 0FFFFFFF7h
0x1800b4dfb  mov     [rbp+0C0h+var_80], 37780014h
0x1800b4e02  mov     [rbp+0C0h+var_90], ecx
0x1800b4e05  xor     ecx, ecx
0x1800b4e07  mov     [rbp+0C0h+var_D0], ecx
0x1800b4e0a  mov     [rbp+0C0h+var_78], rdi
0x1800b4e0e  movups  [rbp+0C0h+var_E0], xmm0
0x1800b4e12  cmp     [rax+30h], edx
0x1800b4e15  jnz     short loc_1800B4E2B
0x1800b4e17  cmp     dword ptr [rax+38h], 14h
0x1800b4e1b  jnz     short loc_1800B4E2B
0x1800b4e1d  mov     rcx, [rax+40h]
0x1800b4e21  movups  xmm0, xmmword ptr [rcx]
0x1800b4e24  movups  [rbp+0C0h+var_E0], xmm0
0x1800b4e28  mov     ecx, [rcx+10h]
0x1800b4e2b  test    r13d, r13d
0x1800b4e2e  jz      short loc_1800B4E36
0x1800b4e30  bts     ecx, 10h
0x1800b4e34  jmp     short loc_1800B4E3A
0x1800b4e36  btr     ecx, 10h
0x1800b4e3a  mov     [rbp+0C0h+var_D0], ecx
0x1800b4e3d  lea     rax, [rbp+0C0h+var_E0]
0x1800b4e41  mov     rcx, [rsp+1C0h+var_190]
0x1800b4e46  lea     r8, [rbp+0C0h+var_B0]
0x1800b4e4a  mov     [rbp+0C0h+var_68], edx
0x1800b4e4d  xor     r9d, r9d
0x1800b4e50  mov     [rbp+0C0h+var_58], rax
0x1800b4e54  mov     [rbp+0C0h+var_60], 14h
0x1800b4e5b  mov     rax, [rcx]
0x1800b4e5e  lea     edx, [r9+4]
0x1800b4e62  mov     rax, [rax+40h]
0x1800b4e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4e6b  mov     ebx, eax
0x1800b4e6d  test    eax, eax
0x1800b4e6f  jns     short loc_1800B4E7C
0x1800b4e71  mov     r9d, 1BAh
0x1800b4e77  jmp     loc_1800B4D9C
0x1800b4e7c  mov     rcx, [rsp+1C0h+var_190]; this
0x1800b4e81  mov     edx, r13d; struct IMessage *
0x1800b4e84  call    ?EncodeBodyForSend@EmailHelper@@YAJPEAUIMessage@@H@Z; EmailHelper::EncodeBodyForSend(IMessage *,int)
0x1800b4e89  mov     ebx, eax
0x1800b4e8b  test    eax, eax
0x1800b4e8d  jns     short loc_1800B4E9A
0x1800b4e8f  mov     r9d, 1BCh
0x1800b4e95  jmp     loc_1800B4D9C
0x1800b4e9a  mov     rcx, [rsp+1C0h+var_190]
0x1800b4e9f  xor     edx, edx
0x1800b4ea1  mov     rax, [rcx]
0x1800b4ea4  mov     rax, [rax+0A0h]
0x1800b4eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4eb0  mov     ebx, eax
0x1800b4eb2  test    eax, eax
0x1800b4eb4  jns     short loc_1800B4EC1
0x1800b4eb6  mov     r9d, 1BFh
0x1800b4ebc  jmp     loc_1800B4D9C
0x1800b4ec1  mov     rdx, [rsp+1C0h+var_190]; struct EmailOperationContext *
0x1800b4ec6  mov     rcx, r12; this
0x1800b4ec9  call    ?SetLastVerbExecutedOnBaseMessage@EmailHelper@@YAJPEAVEmailOperationContext@@PEAUIMessage@@@Z; EmailHelper::SetLastVerbExecutedOnBaseMessage(EmailOperationContext *,IMessage *)
0x1800b4ece  mov     ecx, eax; int
0x1800b4ed0  mov     ebx, eax
0x1800b4ed2  call    ?IsItemNotFoundError@@YAHJ@Z; IsItemNotFoundError(long)
0x1800b4ed7  test    eax, eax
0x1800b4ed9  jnz     short loc_1800B4EEA
0x1800b4edb  test    ecx, ecx
0x1800b4edd  jns     short loc_1800B4EEA
0x1800b4edf  mov     r9d, 1C5h
0x1800b4ee5  jmp     loc_1800B4D9E
0x1800b4eea  mov     edx, r14d; int
0x1800b4eed  lea     rcx, [rbp+0C0h+var_140]; this
0x1800b4ef1  call    ?End@AutoTopLevelTransaction@@UEAAJH@Z; AutoTopLevelTransaction::End(int)
0x1800b4ef6  mov     ebx, eax
0x1800b4ef8  test    eax, eax
0x1800b4efa  jns     short loc_1800B4F07
0x1800b4efc  mov     r9d, 1C9h
0x1800b4f02  jmp     loc_1800B4D9C
0x1800b4f07  lea     rcx, [rsp+1C0h+var_178]
0x1800b4f0c  mov     [rsp+1C0h+var_178], rdi
0x1800b4f11  call    ??$replace@U_SPropValue@@$1?FreeSPropValueArray@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_SPropValue@@AEAV?$auto_array_ptr@U_SPropValue@@$1?FreeSPropValueArray@@YAXPEAU1@@Z@0@@Z; tlx::replace<_SPropValue,&FreeSPropValueArray(_SPropValue *)>(tlx::auto_array_ptr<_SPropValue,&FreeSPropValueArray(_SPropValue *)> &)
0x1800b4f16  mov     rdx, qword ptr [rsp+1C0h+var_160]
0x1800b4f1b  lea     rcx, [rbp+0C0h+var_108]
0x1800b4f1f  mov     r10, rax
0x1800b4f22  call    ?UdmIdToMapiStoreId@@YA?ATUDM_CEMAPI_ID@@AEBUUdmObjectId@@@Z; UdmIdToMapiStoreId(UdmObjectId const &)
0x1800b4f27  mov     r9, r10
0x1800b4f2a  mov     [rsp+1C0h+var_1A0], rdi
0x1800b4f2f  mov     r8d, 3
0x1800b4f35  mov     rcx, r12
0x1800b4f38  mov     edx, [rax+10h]
0x1800b4f3b  movups  xmm0, xmmword ptr [rax]
0x1800b4f3e  mov     [rsp+1C0h+var_150], edx
0x1800b4f42  lea     rdx, [rsp+1C0h+var_160]
0x1800b4f47  movaps  [rsp+1C0h+var_160], xmm0
0x1800b4f4c  call    ?GetSpecialFolderId@EmailOperationContext@@AEAAJTUDM_CEMAPI_ID@@W4UdmEmailSpecialFolderKind@@PEAPEAU_SPropValue@@PEAPEAUIMsgStore@@@Z; EmailOperationContext::GetSpecialFolderId(UDM_CEMAPI_ID,UdmEmailSpecialFolderKind,_SPropValue * *,IMsgStore * *)
0x1800b4f51  mov     ebx, eax
0x1800b4f53  test    eax, eax
0x1800b4f55  jns     short loc_1800B4F83
0x1800b4f57  mov     r9d, 1D1h
0x1800b4f5d  mov     r8, rsi
0x1800b4f60  mov     edx, r14d
0x1800b4f63  mov     ecx, eax
0x1800b4f65  call    Log_HREvent
0x1800b4f6a  mov     rcx, [rsp+1C0h+var_178]; pv
0x1800b4f6f  test    rcx, rcx
0x1800b4f72  jz      loc_1800B4DA9
0x1800b4f78  call    cs:__imp_MAPIFreeBuffer
0x1800b4f7e  jmp     loc_1800B4DA9
0x1800b4f83  mov     rdx, [rsp+1C0h+var_178]
0x1800b4f88  lea     rcx, [rsp+1C0h+var_160]
0x1800b4f8d  mov     r8, [rdx+10h]
0x1800b4f91  mov     edx, [rdx+8]
0x1800b4f94  call    cs:__imp_MapiIdToEmailUdmId
0x1800b4f9a  movsd   xmm0, qword ptr [rsp+1C0h+var_160]
0x1800b4fa0  mov     rcx, [rsp+1C0h+var_178]; pv
0x1800b4fa5  mov     eax, dword ptr [rsp+1C0h+var_160+8]
0x1800b4fa9  movsd   qword ptr [r15+20h], xmm0
  ... truncated ...
```
