# ServiceDataSession::ValidateCallerSecurityForId(UdmObjectId const &,DataSessionAccessType,ObjectAccess *,ObjectAccess *)

- ea: `0x18000bb30`
- end: `0x18000c4cc`
- name: `?ValidateCallerSecurityForId@ServiceDataSession@@QEAAJAEBUUdmObjectId@@W4DataSessionAccessType@@PEAW4ObjectAccess@@2@Z`
- size: `2460`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `27`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800033c0`
- `0x18000d000`
- `0x18001e970`
- `0x18001ec80`
- `0x180020780`
- `0x18002104c`
- `0x180030fdc`
- `0x180060d80`
- `0x180069388`
- `0x18008a490`
- `0x1800a2d4c`
- `0x1800a56b0`
- `0x1800a5940`
- `0x1800a5bb0`
- `0x1800a6410`
- `0x1800aeff0`
- `0x1800b4334`
- `0x1800b45b8`
- `0x1800b7130`
- `0x1800cfd40`
- `0x18011afe0`
- `0x18011bf40`
- `0x18011c930`
- `0x18011fdc0`
- `0x18011ffd0`
- `0x180120220`
- `0x180125b40`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180009990`
- `0x180009a90`
- `0x18000a530`
- `0x18000bb30`
- `0x18000c4e0`
- `0x18000c670`
- `0x18000c740`
- `0x18000defc`
- `0x180021930`
- `0x180021aa4`
- `0x18005e160`
- `0x180061618`
- `0x180079cf4`
- `0x180079e20`
- `0x18007f77c`
- `0x1800810a8`
- `0x1800c8930`
- `0x1800d0978`
- `0x1800d2e9c`
- `0x1800d47f4`
- `0x1800e2f58`
- `0x1800e2fcc`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x18000bbe5`
- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x18000bcc9`
- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x18000bbe5`
- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x18000bcc9`

## string_xrefs

- `0x18000be20`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000be8b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000beff`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000bf17`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000c05a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000c0bc`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000c19e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000c280`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000c33d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000c399`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000c4b5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`

## pseudocode

```c
__int64 __fastcall ServiceDataSession::ValidateCallerSecurityForId(
        struct ServiceDataSession *a1,
        __int64 a2,
        unsigned int a3,
        enum ObjectAccess *a4,
        enum ObjectAccess *a5)
{
  char v5; // r13
  enum ObjectAccess *v10; // r14
  int v11; // edx
  char v12; // r12
  int v13; // eax
  __int64 v14; // r8
  unsigned int v15; // edi
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // r8
  int v20; // eax
  unsigned int v21; // esi
  int v22; // eax
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // r8
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 v30; // r9
  __int64 v31; // r9
  __int64 v32; // rcx
  enum ObjectAccess **v33; // rcx
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rcx
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  unsigned int v43; // r14d
  int v44; // eax
  __int64 v45; // r9
  __int64 v46; // rcx
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  __int64 v52; // r9
  int v53; // eax
  LPVOID ppv; // [rsp+30h] [rbp-41h] BYREF
  _QWORD v55[3]; // [rsp+38h] [rbp-39h] BYREF
  int v56; // [rsp+50h] [rbp-21h]
  __int64 v57; // [rsp+58h] [rbp-19h] BYREF
  __int64 v58; // [rsp+60h] [rbp-11h] BYREF
  _QWORD v59[11]; // [rsp+68h] [rbp-9h] BYREF

  v5 = 0;
  if ( a4 )
    *(_DWORD *)a4 = 2;
  v10 = a5;
  if ( a5 )
    *(_DWORD *)a5 = 2;
  v11 = *(_DWORD *)(a2 + 4);
  if ( v11 == 10 || (unsigned int)(v11 - 11) <= 1 )
  {
    if ( *(_DWORD *)(a2 + 8) == -1 && *(_DWORD *)a2 == -1 && v11 == 10 )
    {
      v5 = 1;
    }
    else if ( !*(_DWORD *)(a2 + 8) && !*(_DWORD *)a2 )
    {
      v12 = 1;
      if ( v11 == 10 )
      {
LABEL_10:
        v55[0] = 0;
        v57 = 0;
        v56 = 0;
        v58 = 0;
        ppv = &CalendarOperationContext::`vftable';
        v13 = UnistoreOperationContext::Initialize((UnistoreOperationContext *)&ppv, a1);
        v15 = v13;
        if ( v13 < 0 )
        {
          Log_HREvent_16((unsigned int)v13, 1, v14, 13);
        }
        else
        {
          a5 = 0;
          v16 = POutlookAppManager_CreateInstance(&a5);
          v15 = v16;
          if ( v16 < 0 )
          {
            v30 = 16;
          }
          else
          {
            v16 = (*(__int64 (__fastcall **)(enum ObjectAccess *, __int64 *))(*(_QWORD *)a5 + 32LL))(a5, &v58);
            v15 = v16;
            if ( v16 >= 0 )
            {
              v56 = 1;
              if ( a5 )
                (*(void (__fastcall **)(enum ObjectAccess *))(*(_QWORD *)a5 + 16LL))(a5);
              v18 = InitializeNamedProperties((struct PoomOperationContext *)&ppv);
              v15 = v18;
              if ( v18 >= 0 )
              {
                if ( v5 )
                {
                  v53 = UnistoreOperationContext::ValidateCallerSecurity(&ppv, 1, 0);
                  v15 = v53;
                  if ( v53 >= 0 )
                    goto LABEL_19;
                  v36 = 1311;
                }
                else
                {
                  if ( !v12 )
                  {
                    v20 = UnistoreOperationContext::ValidateCallerSecurityForId(
                            (UnistoreOperationContext *)&ppv,
                            (const struct UdmObjectId *)a2,
                            a4,
                            v10);
                    v21 = v20;
                    if ( v20 >= 0 )
                    {
LABEL_19:
                      PoomOperationContext::~PoomOperationContext((PoomOperationContext *)&ppv);
                      return 0;
                    }
                    if ( v20 != -2147023728 )
                      Log_HREvent(
                        (unsigned int)v20,
                        1,
                        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
                        1319);
                    v15 = v21;
                    goto LABEL_60;
                  }
                  v53 = UnistoreOperationContext::ValidateCallerSecurity(&ppv, 0, 0);
                  v15 = v53;
                  if ( v53 >= 0 )
                    goto LABEL_19;
                  v36 = 1315;
                }
                v37 = (unsigned int)v53;
                goto LABEL_58;
              }
              v31 = 11;
              v32 = (unsigned int)v18;
LABEL_42:
              Log_HREvent_5(v32, 1, v19, v31);
              Log_HREvent(
                v15,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
                1307);
              if ( v58 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
              if ( v57 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
              if ( v55[0] )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v55[0] + 16LL))(v55[0]);
              return v15;
            }
            v30 = 17;
          }
          Log_HREvent_16((unsigned int)v16, 1, v17, v30);
          if ( a5 )
            (*(void (__fastcall **)(enum ObjectAccess *))(*(_QWORD *)a5 + 16LL))(a5);
        }
        v31 = 10;
        v32 = v15;
        goto LABEL_42;
      }
    }
    v12 = 0;
    goto LABEL_10;
  }
  if ( v11 == 36 || v11 == 37 || v11 == 458754 )
  {
    v55[0] = 0;
    ppv = &ContactOperationContext::`vftable';
    v57 = 0;
    v56 = 0;
    v58 = 0;
    v22 = UnistoreOperationContext::Initialize((UnistoreOperationContext *)&ppv, a1);
    v15 = v22;
    if ( v22 < 0 )
    {
      Log_HREvent_16((unsigned int)v22, 1, v23, 13);
    }
    else
    {
      a5 = 0;
      v24 = POutlookAppManager_CreateInstance(&a5);
      v15 = v24;
      if ( v24 < 0 )
      {
        v34 = 16;
      }
      else
      {
        v24 = (*(__int64 (__fastcall **)(enum ObjectAccess *, __int64 *))(*(_QWORD *)a5 + 32LL))(a5, &v58);
        v15 = v24;
        if ( v24 >= 0 )
        {
          v56 = 1;
          if ( a5 )
            (*(void (__fastcall **)(enum ObjectAccess *))(*(_QWORD *)a5 + 16LL))(a5);
          if ( *(_DWORD *)(a2 + 4) == 458754 )
          {
            if ( a4 )
              *(_DWORD *)a4 = 2;
            if ( v10 )
              *(_DWORD *)v10 = 0;
            goto LABEL_30;
          }
          v26 = UnistoreOperationContext::ValidateCallerSecurityForId(
                  (UnistoreOperationContext *)&ppv,
                  (const struct UdmObjectId *)a2,
                  a4,
                  v10);
          v15 = v26;
          if ( v26 == -2147024891 )
          {
            v15 = -2147023728;
          }
          else if ( v26 >= 0 )
          {
LABEL_30:
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v58);
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v57);
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(v55);
            return 0;
          }
          v36 = 1334;
LABEL_57:
          v37 = v15;
LABEL_58:
          Log_HREvent(
            v37,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
            v36);
LABEL_60:
          PoomOperationContext::~PoomOperationContext((PoomOperationContext *)&ppv);
          return v15;
        }
        v34 = 17;
      }
      Log_HREvent_16((unsigned int)v24, 1, v25, v34);
      if ( a5 )
        (*(void (__fastcall **)(enum ObjectAccess *))(*(_QWORD *)a5 + 16LL))(a5);
    }
    Log_HREvent_17(v15, 1, v35, 9);
    v36 = 1325;
    goto LABEL_57;
  }
  if ( v11 == 43 || v11 == 44 )
  {
    v55[0] = 0;
    v57 = 0;
    v56 = 0;
    ATL::CComPtr<ServiceDataSession>::operator=(v55, 0);
    v58 = 0;
    ppv = &AnnotationOperationContext::`vftable';
    v38 = PoomOperationContext::Initialize((PoomOperationContext *)&ppv, a1);
    v15 = v38;
    if ( v38 < 0 )
    {
      v36 = 1339;
      goto LABEL_112;
    }
    v39 = AnnotationOperationContext::ValidateCallerSecurityForId(
            (AnnotationOperationContext *)&ppv,
            (const struct UdmObjectId *)a2,
            0);
    v15 = v39;
    if ( v39 == -2147024891 )
    {
      v15 = -2147023728;
    }
    else if ( v39 >= 0 )
    {
      goto LABEL_19;
    }
    v36 = 1348;
LABEL_119:
    v37 = v15;
    goto LABEL_58;
  }
  if ( v11 == 4 || v11 == 5 || v11 == 6 || v11 == 7 || (unsigned int)(v11 - 8) <= 1 )
  {
    v55[0] = 0;
    ppv = &EmailOperationContext::`vftable';
    v57 = 0;
    v56 = 0;
    v58 = 0;
    v59[0] = 0;
    v40 = EmailOperationContext::Initialize((EmailOperationContext *)&ppv, a1);
    v15 = v40;
    if ( v40 < 0 )
    {
      Log_HREvent(
        (unsigned int)v40,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        1353);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(v59);
      goto LABEL_60;
    }
    v41 = UnistoreOperationContext::ValidateCallerSecurityForId(
            (UnistoreOperationContext *)&ppv,
            (const struct UdmObjectId *)a2,
            a4,
            v10);
    v15 = v41;
    if ( v41 == -2147024891 )
    {
      v15 = -2147023728;
    }
    else if ( v41 >= 0 )
    {
      EmailOperationContext::~EmailOperationContext((EmailOperationContext *)&ppv);
      return 0;
    }
    Log_HREvent(
      v15,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      1362);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(v59);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v58);
    goto LABEL_50;
  }
  if ( v11 != 33 && v11 != 34 && v11 != 35 && v11 != 42 )
  {
    if ( v11 == 1 )
    {
      a5 = 0;
      if ( a1 )
      {
        (*(void (__fastcall **)(struct ServiceDataSession *))(*(_QWORD *)a1 + 8LL))(a1);
        a5 = a1;
      }
      if ( (int)CallHistoryOperationContext::ValidateCallerSecurity(&a5, 2, 0, 1) < 0 )
      {
        v44 = CallHistoryOperationContext::ValidateCallerSecurityForId(
                (CallHistoryOperationContext *)&a5,
                (const struct UdmObjectId *)a2,
                a4,
                v10,
                0);
        v15 = v44;
        if ( v44 == -2147024891 )
        {
          v15 = -2147023728;
LABEL_121:
          Log_HREvent(
            v15,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
            1390);
LABEL_123:
          v33 = &a5;
          goto LABEL_51;
        }
        if ( v44 < 0 )
          goto LABEL_121;
      }
      v15 = 0;
      goto LABEL_123;
    }
    if ( v11 == 41 )
    {
      v55[0] = 0;
      ppv = &UserDataAccountOperationContext::`vftable';
      v57 = 0;
      v56 = 0;
      v27 = UnistoreOperationContext::Initialize((UnistoreOperationContext *)&ppv, a1);
      v15 = v27;
      if ( v27 < 0 )
      {
        Log_HREvent(
          (unsigned int)v27,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          1398);
LABEL_50:
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v57);
        v33 = (enum ObjectAccess **)v55;
LABEL_51:
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(v33);
        return v15;
      }
      v28 = UnistoreOperationContext::ValidateCallerSecurityForId(
              (UnistoreOperationContext *)&ppv,
              (const struct UdmObjectId *)a2,
              a4,
              v10);
      v15 = v28;
      if ( v28 == -2147024891 )
      {
        v15 = -2147023728;
      }
      else if ( v28 >= 0 )
      {
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v57);
        if ( v55[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v55[0] + 16LL))(v55[0]);
        return 0;
      }
      v45 = 1407;
      v46 = v15;
LABEL_98:
      Log_HREvent(
        v46,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        v45);
      UnistoreOperationContext::~UnistoreOperationContext((UnistoreOperationContext *)&ppv);
      return v15;
    }
    if ( v11 != 49 && v11 != 50 )
    {
      if ( (unsigned int)(v11 - 38) > 1 )
      {
        v49 = ServiceDataSession::ValidateCallerSecurity(a1, 0, 0x100000u, 1);
        v15 = v49;
        if ( v49 >= 0 )
          return 0;
        Log_HREvent(
          (unsigned int)v49,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          1440);
        return v15;
      }
      v55[0] = 0;
      v57 = 0;
      v56 = 0;
      ATL::CComPtr<ServiceDataSession>::operator=(v55, 0);
      ppv = &ContactGroupOperationContext::`vftable';
      v47 = UnistoreOperationContext::Initialize((UnistoreOperationContext *)&ppv, a1);
      v15 = v47;
      if ( v47 >= 0 )
      {
        v48 = UnistoreOperationContext::ValidateCallerSecurityForId(
                (UnistoreOperationContext *)&ppv,
                (const struct UdmObjectId *)a2,
                a4,
                v10);
        v15 = v48;
        if ( v48 == -2147024891 )
        {
          v15 = -2147023728;
        }
        else if ( v48 >= 0 )
        {
          UnistoreOperationContext::~UnistoreOperationContext((UnistoreOperationContext *)&ppv);
          return 0;
        }
        v45 = 1435;
        v46 = v15;
      }
      else
      {
        v45 = 1426;
        v46 = (unsigned int)v47;
      }
      goto LABEL_98;
    }
    v55[0] = 0;
    v57 = 0;
    v56 = 0;
    ATL::CComPtr<ServiceDataSession>::operator=(v55, 0);
    v58 = 0;
    ppv = &TaskOperationContext::`vftable';
    v38 = PoomOperationContext::Initialize((PoomOperationContext *)&ppv, a1);
    v15 = v38;
    if ( v38 < 0 )
    {
      v36 = 1412;
LABEL_112:
      v37 = (unsigned int)v38;
      goto LABEL_58;
    }
    v50 = UnistoreOperationContext::ValidateCallerSecurityForId(
            (UnistoreOperationContext *)&ppv,
            (const struct UdmObjectId *)a2,
            a4,
            v10);
    v15 = v50;
    if ( v50 == -2147024891 )
    {
      v15 = -2147023728;
    }
    else if ( v50 >= 0 )
    {
      goto LABEL_19;
    }
    v36 = 1421;
    goto LABEL_119;
  }
  v42 = ServiceDataSession::ValidateCallerSecurity(a1, 0, 0x24u, 1);
  v43 = v42;
  if ( v42 >= 0 )
  {
    ChatOperationContext::ChatOperationContext((ChatOperationContext *)&ppv);
    v51 = ChatOperationContext::Initialize(&ppv, a1);
    v15 = v51;
    if ( v51 >= 0 )
    {
      v51 = ChatOperationContext::ValidateCallerSecurityForId(&ppv, a2, a3);
      v15 = v51;
      if ( v51 >= 0 )
      {
        ChatOperationContext::~ChatOperationContext((ChatOperationContext *)&ppv);
        return 0;
      }
      v52 = 1373;
    }
    else
    {
      v52 = 1372;
    }
    Log_HREvent(
      (unsigned int)v51,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      v52);
    ChatOperationContext::~ChatOperationContext((ChatOperationContext *)&ppv);
    return v15;
  }
  Log_HREvent(
    (unsigned int)v42,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
    1369);
  return v43;
}

```

## disassembly

```asm
0x18000bb30  push    rbp
0x18000bb32  push    rbx
0x18000bb33  push    rsi
0x18000bb34  push    rdi
0x18000bb35  push    r12
0x18000bb37  push    r13
0x18000bb39  push    r14
0x18000bb3b  push    r15
0x18000bb3d  lea     rbp, [rsp-17h]
0x18000bb42  sub     rsp, 88h
0x18000bb49  xor     r13d, r13d
0x18000bb4c  mov     r15, r9
0x18000bb4f  mov     r12d, r8d
0x18000bb52  mov     rsi, rdx
0x18000bb55  mov     rdi, rcx
0x18000bb58  mov     eax, 2
0x18000bb5d  test    r9, r9
0x18000bb60  jz      short loc_18000BB65
0x18000bb62  mov     [r9], eax
0x18000bb65  mov     r14, [rbp+4Fh+arg_20]
0x18000bb69  test    r14, r14
0x18000bb6c  jnz     loc_18000C146
0x18000bb72  mov     edx, [rdx+4]
0x18000bb75  mov     ecx, edx
0x18000bb77  sub     ecx, 0Ah
0x18000bb7a  jz      short loc_18000BB8A
0x18000bb7c  sub     ecx, 1
0x18000bb7f  jz      short loc_18000BB8A
0x18000bb81  cmp     ecx, 1
0x18000bb84  jnz     loc_18000BC7A
0x18000bb8a  or      eax, 0FFFFFFFFh
0x18000bb8d  mov     ebx, 1
0x18000bb92  cmp     [rsi+8], eax
0x18000bb95  jz      loc_18000C421
0x18000bb9b  xor     eax, eax
0x18000bb9d  cmp     [rsi+8], eax
0x18000bba0  jz      loc_18000C43C
0x18000bba6  mov     r12b, al
0x18000bba9  mov     [rbp+4Fh+var_88], rax
0x18000bbad  lea     rcx, [rbp+4Fh+ppv]; this
0x18000bbb1  mov     [rbp+4Fh+var_68], rax
0x18000bbb5  mov     rdx, rdi; struct ServiceDataSession *
0x18000bbb8  mov     [rbp+4Fh+var_70], eax
0x18000bbbb  mov     [rbp+4Fh+var_60], rax
0x18000bbbf  lea     rax, ??_7CalendarOperationContext@@6B@; const CalendarOperationContext::`vftable'
0x18000bbc6  mov     [rbp+4Fh+ppv], rax
0x18000bbca  call    ?Initialize@UnistoreOperationContext@@UEAAJPEAVServiceDataSession@@@Z; UnistoreOperationContext::Initialize(ServiceDataSession *)
0x18000bbcf  mov     edi, eax
0x18000bbd1  test    eax, eax
0x18000bbd3  js      loc_18000C455
0x18000bbd9  lea     rcx, [rbp+4Fh+arg_20]
0x18000bbdd  mov     [rbp+4Fh+arg_20], 0
0x18000bbe5  call    cs:__imp_POutlookAppManager_CreateInstance
0x18000bbeb  mov     edi, eax
0x18000bbed  test    eax, eax
0x18000bbef  js      loc_18000BEB2
0x18000bbf5  mov     rcx, [rbp+4Fh+arg_20]
0x18000bbf9  lea     rdx, [rbp+4Fh+var_60]
0x18000bbfd  mov     rax, [rcx]
0x18000bc00  mov     rax, [rax+20h]
0x18000bc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc09  mov     edi, eax
0x18000bc0b  test    eax, eax
0x18000bc0d  js      loc_18000BDE7
0x18000bc13  mov     rcx, [rbp+4Fh+arg_20]
0x18000bc17  mov     [rbp+4Fh+var_70], ebx
0x18000bc1a  test    rcx, rcx
0x18000bc1d  jz      short loc_18000BC2B
0x18000bc1f  mov     rax, [rcx]
0x18000bc22  mov     rax, [rax+10h]
0x18000bc26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc2b  lea     rcx, [rbp+4Fh+ppv]; struct PoomOperationContext *
0x18000bc2f  call    ?InitializeNamedProperties@@YAJPEAVPoomOperationContext@@@Z; InitializeNamedProperties(PoomOperationContext *)
0x18000bc34  mov     edi, eax
0x18000bc36  test    eax, eax
0x18000bc38  js      loc_18000BF4C
0x18000bc3e  lea     rcx, [rbp+4Fh+ppv]; this
0x18000bc42  test    r13b, r13b
0x18000bc45  jnz     loc_18000C469
0x18000bc4b  test    r12b, r12b
0x18000bc4e  jnz     loc_18000C485
0x18000bc54  mov     r9, r14; enum ObjectAccess *
0x18000bc57  mov     r8, r15; enum ObjectAccess *
0x18000bc5a  mov     rdx, rsi; struct UdmObjectId *
0x18000bc5d  call    ?ValidateCallerSecurityForId@UnistoreOperationContext@@UEAAJAEBUUdmObjectId@@PEAW4ObjectAccess@@1@Z; UnistoreOperationContext::ValidateCallerSecurityForId(UdmObjectId const &,ObjectAccess *,ObjectAccess *)
0x18000bc62  mov     esi, eax
0x18000bc64  test    eax, eax
0x18000bc66  js      loc_18000C4A6
0x18000bc6c  lea     rcx, [rbp+4Fh+ppv]; this
0x18000bc70  call    ??1PoomOperationContext@@QEAA@XZ; PoomOperationContext::~PoomOperationContext(void)
0x18000bc75  jmp     loc_18000BDE0
0x18000bc7a  mov     ecx, edx
0x18000bc7c  mov     r8d, 24h ; '$'; unsigned int
0x18000bc82  sub     ecx, r8d
0x18000bc85  jz      short loc_18000BC90
0x18000bc87  sub     ecx, 1
0x18000bc8a  jnz     loc_18000C14E
0x18000bc90  lea     rax, ??_7ContactOperationContext@@6B@; const ContactOperationContext::`vftable'
0x18000bc97  mov     [rbp+4Fh+var_88], r13
0x18000bc9b  mov     rdx, rdi; struct ServiceDataSession *
0x18000bc9e  mov     [rbp+4Fh+ppv], rax
0x18000bca2  lea     rcx, [rbp+4Fh+ppv]; this
0x18000bca6  mov     [rbp+4Fh+var_68], r13
0x18000bcaa  mov     [rbp+4Fh+var_70], r13d
0x18000bcae  mov     [rbp+4Fh+var_60], r13
0x18000bcb2  call    ?Initialize@UnistoreOperationContext@@UEAAJPEAVServiceDataSession@@@Z; UnistoreOperationContext::Initialize(ServiceDataSession *)
0x18000bcb7  mov     edi, eax
0x18000bcb9  test    eax, eax
0x18000bcbb  js      loc_18000C3DD
0x18000bcc1  lea     rcx, [rbp+4Fh+arg_20]
0x18000bcc5  mov     [rbp+4Fh+arg_20], r13
0x18000bcc9  call    cs:__imp_POutlookAppManager_CreateInstance
0x18000bccf  mov     edi, eax
0x18000bcd1  test    eax, eax
0x18000bcd3  js      loc_18000BF41
0x18000bcd9  mov     rcx, [rbp+4Fh+arg_20]
0x18000bcdd  lea     rdx, [rbp+4Fh+var_60]
0x18000bce1  mov     rax, [rcx]
0x18000bce4  mov     rax, [rax+20h]
0x18000bce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bced  mov     edi, eax
0x18000bcef  test    eax, eax
0x18000bcf1  js      loc_18000BEBD
0x18000bcf7  mov     rcx, [rbp+4Fh+arg_20]
0x18000bcfb  mov     ebx, 1
0x18000bd00  mov     [rbp+4Fh+var_70], ebx
0x18000bd03  test    rcx, rcx
0x18000bd06  jz      short loc_18000BD14
0x18000bd08  mov     rax, [rcx]
0x18000bd0b  mov     rax, [rax+10h]
0x18000bd0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd14  cmp     dword ptr [rsi+4], 70002h
0x18000bd1b  jz      loc_18000C3F4
0x18000bd21  mov     r9, r14; enum ObjectAccess *
0x18000bd24  lea     rcx, [rbp+4Fh+ppv]; this
0x18000bd28  mov     r8, r15; enum ObjectAccess *
0x18000bd2b  mov     rdx, rsi; struct UdmObjectId *
0x18000bd2e  call    ?ValidateCallerSecurityForId@UnistoreOperationContext@@UEAAJAEBUUdmObjectId@@PEAW4ObjectAccess@@1@Z; UnistoreOperationContext::ValidateCallerSecurityForId(UdmObjectId const &,ObjectAccess *,ObjectAccess *)
0x18000bd33  mov     edi, eax
0x18000bd35  cmp     eax, 80070005h
0x18000bd3a  jz      loc_18000C411
0x18000bd40  test    eax, eax
0x18000bd42  js      loc_18000C416
0x18000bd48  lea     rcx, [rbp+4Fh+var_60]
0x18000bd4c  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000bd51  lea     rcx, [rbp+4Fh+var_68]
0x18000bd55  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000bd5a  lea     rcx, [rbp+4Fh+var_88]
0x18000bd5e  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000bd63  jmp     short loc_18000BDE0
0x18000bd65  cmp     edx, 29h ; ')'
0x18000bd68  jnz     loc_18000C1B8
0x18000bd6e  lea     rax, ??_7UserDataAccountOperationContext@@6B@; const UserDataAccountOperationContext::`vftable'
0x18000bd75  mov     [rbp+4Fh+var_88], r13
0x18000bd79  mov     rdx, rdi; struct ServiceDataSession *
0x18000bd7c  mov     [rbp+4Fh+ppv], rax
0x18000bd80  lea     rcx, [rbp+4Fh+ppv]; this
0x18000bd84  mov     [rbp+4Fh+var_68], r13
0x18000bd88  mov     [rbp+4Fh+var_70], r13d
0x18000bd8c  call    ?Initialize@UnistoreOperationContext@@UEAAJPEAVServiceDataSession@@@Z; UnistoreOperationContext::Initialize(ServiceDataSession *)
0x18000bd91  mov     edi, eax
0x18000bd93  test    eax, eax
0x18000bd95  js      loc_18000BE85
0x18000bd9b  mov     r9, r14; enum ObjectAccess *
0x18000bd9e  lea     rcx, [rbp+4Fh+ppv]; this
0x18000bda2  mov     r8, r15; enum ObjectAccess *
0x18000bda5  mov     rdx, rsi; struct UdmObjectId *
0x18000bda8  call    ?ValidateCallerSecurityForId@UnistoreOperationContext@@UEAAJAEBUUdmObjectId@@PEAW4ObjectAccess@@1@Z; UnistoreOperationContext::ValidateCallerSecurityForId(UdmObjectId const &,ObjectAccess *,ObjectAccess *)
0x18000bdad  mov     edi, eax
0x18000bdaf  cmp     eax, 80070005h
0x18000bdb4  jz      loc_18000C17B
0x18000bdba  test    eax, eax
0x18000bdbc  js      loc_18000C180
0x18000bdc2  lea     rcx, [rbp+4Fh+var_68]
0x18000bdc6  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000bdcb  mov     rcx, [rbp+4Fh+var_88]
0x18000bdcf  test    rcx, rcx
0x18000bdd2  jz      short loc_18000BDE0
0x18000bdd4  mov     rax, [rcx]
0x18000bdd7  mov     rax, [rax+10h]
0x18000bddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde0  xor     eax, eax
0x18000bde2  jmp     loc_18000BE71
0x18000bde7  mov     r9d, 11h
0x18000bded  mov     edx, ebx
0x18000bdef  mov     ecx, eax
0x18000bdf1  call    Log_HREvent_16
0x18000bdf6  mov     rcx, [rbp+4Fh+arg_20]
0x18000bdfa  test    rcx, rcx
0x18000bdfd  jz      short loc_18000BE0B
0x18000bdff  mov     rax, [rcx]
0x18000be02  mov     rax, [rax+10h]
0x18000be06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be0b  mov     r9d, 0Ah
0x18000be11  mov     ecx, edi
0x18000be13  mov     edx, ebx
0x18000be15  call    Log_HREvent_5
0x18000be1a  mov     r9d, 51Bh
0x18000be20  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000be27  mov     edx, ebx
0x18000be29  mov     ecx, edi
0x18000be2b  call    Log_HREvent
0x18000be30  mov     rcx, [rbp+4Fh+var_60]
0x18000be34  test    rcx, rcx
0x18000be37  jz      short loc_18000BE45
0x18000be39  mov     rax, [rcx]
0x18000be3c  mov     rax, [rax+10h]
0x18000be40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be45  mov     rcx, [rbp+4Fh+var_68]
0x18000be49  test    rcx, rcx
0x18000be4c  jz      short loc_18000BE5A
0x18000be4e  mov     rax, [rcx]
0x18000be51  mov     rax, [rax+10h]
0x18000be55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be5a  mov     rcx, [rbp+4Fh+var_88]
0x18000be5e  test    rcx, rcx
0x18000be61  jz      short loc_18000BE6F
0x18000be63  mov     rdx, [rcx]
0x18000be66  mov     rax, [rdx+10h]
0x18000be6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be6f  mov     eax, edi
0x18000be71  add     rsp, 88h
0x18000be78  pop     r15
0x18000be7a  pop     r14
0x18000be7c  pop     r13
0x18000be7e  pop     r12
0x18000be80  pop     rdi
0x18000be81  pop     rsi
0x18000be82  pop     rbx
0x18000be83  pop     rbp
0x18000be84  retn
0x18000be85  mov     r9d, 576h
0x18000be8b  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000be92  mov     edx, 1
0x18000be97  mov     ecx, edi
0x18000be99  call    Log_HREvent
0x18000be9e  lea     rcx, [rbp+4Fh+var_68]
0x18000bea2  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000bea7  lea     rcx, [rbp+4Fh+var_88]
0x18000beab  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000beb0  jmp     short loc_18000BE6F
0x18000beb2  mov     r9d, 10h
0x18000beb8  jmp     loc_18000BDED
0x18000bebd  mov     r9d, 11h
0x18000bec3  mov     ebx, 1
0x18000bec8  mov     ecx, eax
0x18000beca  mov     edx, ebx
0x18000becc  call    Log_HREvent_16
0x18000bed1  mov     rcx, [rbp+4Fh+arg_20]
0x18000bed5  test    rcx, rcx
0x18000bed8  jz      short loc_18000BEE6
0x18000beda  mov     rax, [rcx]
0x18000bedd  mov     rax, [rax+10h]
0x18000bee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee6  mov     r9d, 9
0x18000beec  mov     edx, ebx
0x18000beee  mov     ecx, edi
0x18000bef0  call    Log_HREvent_17
0x18000bef5  mov     r9d, 52Dh
0x18000befb  mov     ecx, edi
0x18000befd  mov     edx, ebx
0x18000beff  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bf06  call    Log_HREvent
0x18000bf0b  lea     rcx, [rbp+4Fh+ppv]
0x18000bf0f  jmp     short loc_18000BF37
0x18000bf11  mov     r9d, 549h
0x18000bf17  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bf1e  mov     edx, 1
0x18000bf23  mov     ecx, edi
0x18000bf25  call    Log_HREvent
0x18000bf2a  lea     rcx, [rbp+4Fh+var_58]
0x18000bf2e  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000bf33  lea     rcx, [rbp+4Fh+ppv]; this
0x18000bf37  call    ??1PoomOperationContext@@QEAA@XZ; PoomOperationContext::~PoomOperationContext(void)
0x18000bf3c  jmp     loc_18000BE6F
0x18000bf41  mov     r9d, 10h
0x18000bf47  jmp     loc_18000BEC3
0x18000bf4c  mov     r9d, 0Bh
0x18000bf52  mov     ecx, eax
0x18000bf54  jmp     loc_18000BE13
0x18000bf59  mov     ecx, edx
0x18000bf5b  sub     ecx, 2Bh ; '+'
0x18000bf5e  jnz     loc_18000C15F
0x18000bf64  lea     rax, ??_7UnistoreOperationContext@@6B@; const UnistoreOperationContext::`vftable'
0x18000bf6b  mov     [rbp+4Fh+var_88], r13
0x18000bf6f  xor     edx, edx
0x18000bf71  mov     [rbp+4Fh+ppv], rax
0x18000bf75  lea     rcx, [rbp+4Fh+var_88]
0x18000bf79  mov     [rbp+4Fh+var_68], r13
0x18000bf7d  mov     [rbp+4Fh+var_70], r13d
0x18000bf81  call    ??4?$CComPtr@VServiceDataSession@@@ATL@@QEAAPEAVServiceDataSession@@PEAV2@@Z; ATL::CComPtr<ServiceDataSession>::operator=(ServiceDataSession *)
0x18000bf86  lea     rax, ??_7AnnotationOperationContext@@6B@; const AnnotationOperationContext::`vftable'
0x18000bf8d  mov     [rbp+4Fh+var_60], r13
0x18000bf91  mov     rdx, rdi; struct ServiceDataSession *
0x18000bf94  mov     [rbp+4Fh+ppv], rax
0x18000bf98  lea     rcx, [rbp+4Fh+ppv]; this
0x18000bf9c  call    ?Initialize@PoomOperationContext@@UEAAJPEAVServiceDataSession@@@Z; PoomOperationContext::Initialize(ServiceDataSession *)
0x18000bfa1  mov     edi, eax
0x18000bfa3  test    eax, eax
0x18000bfa5  js      loc_18000C2E0
  ... truncated ...
```
