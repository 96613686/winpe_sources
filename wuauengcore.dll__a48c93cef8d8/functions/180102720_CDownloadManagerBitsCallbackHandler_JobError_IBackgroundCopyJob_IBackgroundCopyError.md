# CDownloadManagerBitsCallbackHandler::JobError(IBackgroundCopyJob *,IBackgroundCopyError *)

- ea: `0x180102720`
- end: `0x180102b6f`
- name: `?JobError@CDownloadManagerBitsCallbackHandler@@UEAAJPEAUIBackgroundCopyJob@@PEAUIBackgroundCopyError@@@Z`
- size: `1103`
- prototype: `__int64 __fastcall(CDownloadManagerBitsCallbackHandler *__hidden this, struct IBackgroundCopyJob *, struct IBackgroundCopyError *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000def4`
- `0x1800f45e0`
- `0x180102720`
- `0x180102b78`
- `0x18012b618`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010291f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801029eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102aa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010291f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801029eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102aa8`
- `OLEAUT32!__imp_VariantInit` at `0x18010288b`
- `OLEAUT32!__imp_VariantInit` at `0x18010288b`
- `OLEAUT32!__imp_VariantClear` at `0x1801028cb`
- `OLEAUT32!__imp_VariantClear` at `0x1801028e0`
- `OLEAUT32!__imp_VariantClear` at `0x1801028cb`
- `OLEAUT32!__imp_VariantClear` at `0x1801028e0`

## string_xrefs

- `0x180102761`: `C:\__w\1\s\src\Client\Engine\Agent\DownloadManagerBitsCallbackHandler.cpp`
- `0x1801027d8`: `C:\__w\1\s\src\Client\Engine\Agent\DownloadManagerBitsCallbackHandler.cpp`
- `0x1801028b5`: `C:\__w\1\s\src\Client\Engine\Agent\DownloadManagerBitsCallbackHandler.cpp`
- `0x180102a85`: `C:\__w\1\s\src\Client\Engine\Agent\DownloadManagerBitsCallbackHandler.cpp`
- `0x180102ad2`: `C:\__w\1\s\src\Client\Engine\Agent\DownloadManagerBitsCallbackHandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CDownloadManagerBitsCallbackHandler::JobError(
        CDownloadManagerCallbackHandler **this,
        struct IBackgroundCopyJob *a2,
        struct IBackgroundCopyError *a3)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  int v8; // esi
  __int64 v9; // rdx
  int v11; // eax
  struct IBackgroundCopyErrorVtbl *lpVtbl; // rax
  __int64 v13; // rbx
  int (__fastcall *v14)(__int64, LPVOID *); // rdi
  __int64 v15; // rbx
  int (__fastcall *v16)(__int64, LPVOID *); // rdi
  void *v17; // rbx
  int v18; // eax
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, LPVOID *); // rdi
  int v21; // eax
  int v22; // [rsp+20h] [rbp-79h]
  int v23; // [rsp+20h] [rbp-79h]
  __int64 v24; // [rsp+30h] [rbp-69h] BYREF
  int v25; // [rsp+38h] [rbp-61h] BYREF
  unsigned int v26; // [rsp+3Ch] [rbp-5Dh] BYREF
  BG_JOB_STATE v27; // [rsp+40h] [rbp-59h] BYREF
  __int64 v28; // [rsp+48h] [rbp-51h] BYREF
  __int64 v29; // [rsp+50h] [rbp-49h] BYREF
  _DWORD v30[2]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v31; // [rsp+60h] [rbp-39h]
  LPVOID pv[2]; // [rsp+68h] [rbp-31h] BYREF
  LPVOID v33[2]; // [rsp+78h] [rbp-21h] BYREF
  __int64 v34; // [rsp+88h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-9h] BYREF
  GUID v36; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( a2 )
  {
    if ( !a3 )
    {
      v6 = 137;
      goto LABEL_3;
    }
    WUTrace(0, 0, 2, 5, 0, L"JobError() callback received.");
    v36 = GUID_NULL;
    v8 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *))a2->lpVtbl->GetId)(a2, &v36);
    if ( v8 < 0 )
    {
      v9 = 142;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\DownloadManagerBitsCallbackHandler.cpp",
        (const char *)(unsigned int)v8,
        v23);
      return (unsigned int)v8;
    }
    v27 = BG_JOB_STATE_ERROR;
    v8 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, BG_JOB_STATE *))a2->lpVtbl->GetState)(a2, &v27);
    if ( v8 < 0 )
    {
      v9 = 145;
      goto LABEL_8;
    }
    v25 = 0;
    v26 = 0;
    v8 = ((__int64 (__fastcall *)(struct IBackgroundCopyError *, int *, unsigned int *))a3->lpVtbl->GetError)(
           a3,
           &v25,
           &v26);
    if ( v8 < 0 )
    {
      v9 = 149;
      goto LABEL_8;
    }
    *(_OWORD *)pv = 0;
    *(_OWORD *)v33 = 0;
    v30[1] = v25;
    v31 = v26;
    v30[0] = 1;
    v34 = 0;
    if ( ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_18995a26_bf59_4abe_9f8b_d5092d5a2405,
           &v34) < 0 )
    {
      HIDWORD(v31) = 0;
    }
    else
    {
      VariantInit(&pvarg);
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v34 + 32LL))(v34, 0, &pvarg);
      v7 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\DownloadManagerBitsCallbackHandler.cpp",
          (const char *)(unsigned int)v11,
          v23);
        VariantClear(&pvarg);
LABEL_59:
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        tagDownloadJobError::~tagDownloadJobError((tagDownloadJobError *)v30);
        return v7;
      }
      HIDWORD(v31) = pvarg.lVal;
      VariantClear(&pvarg);
    }
    lpVtbl = a3->lpVtbl;
    v24 = 0;
    if ( ((int (__fastcall *)(struct IBackgroundCopyError *, __int64 *))lpVtbl->GetFile)(a3, &v24) < 0 )
      goto LABEL_46;
    v13 = v24;
    v14 = *(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v24 + 24LL);
    if ( pv[1] )
    {
      CoTaskMemFree(pv[1]);
      pv[1] = 0;
    }
    if ( v14(v13, &pv[1]) < 0 )
    {
      if ( pv[1] )
        CoTaskMemFree(pv[1]);
      pv[1] = 0;
    }
    v15 = v24;
    v16 = *(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v24 + 32LL);
    if ( pv[0] )
    {
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
    }
    if ( v16(v15, pv) >= 0 )
    {
      if ( !pv[0] )
      {
LABEL_32:
        pv[0] = 0;
LABEL_33:
        v29 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v24)(
               v24,
               &GUID_85c1657f_dafc_40e8_8834_df18ea25717e,
               &v29) >= 0 )
        {
          *(_QWORD *)&pvarg.vt = 0;
          if ( (*(int (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v29 + 112LL))(v29, 1, &pvarg) >= 0 )
          {
            v17 = *(void **)&pvarg.vt;
            if ( v33[0] )
              CoTaskMemFree(v33[0]);
            v33[0] = v17;
          }
        }
        v28 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v24)(
               v24,
               &GUID_b76b9699_e99e_4101_803f_a20e325d93e2,
               &v28) >= 0 )
        {
          v19 = v28;
          v20 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v28 + 24LL);
          if ( v33[1] )
          {
            CoTaskMemFree(v33[1]);
            v33[1] = 0;
          }
          v21 = v20(v19, &v33[1]);
          v7 = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCE,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\DownloadManagerBitsCallbackHandler.cpp",
              (const char *)(unsigned int)v21,
              v23);
            if ( v28 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            if ( v29 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            goto LABEL_57;
          }
        }
        else
        {
          if ( v33[1] )
            CoTaskMemFree(v33[1]);
          v33[1] = 0;
        }
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
LABEL_46:
        *(GUID *)&pvarg.vt = v36;
        v18 = CDownloadManagerCallbackHandler::JobError(
                this[1],
                (struct _GUID *)&pvarg,
                v27,
                (struct tagDownloadJobError *)v30);
        v7 = v18;
        if ( v18 >= 0 )
          v7 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD2,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\DownloadManagerBitsCallbackHandler.cpp",
            (const char *)(unsigned int)v18,
            v23);
LABEL_57:
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        goto LABEL_59;
      }
      if ( *(_WORD *)pv[0] )
        goto LABEL_33;
    }
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    goto LABEL_32;
  }
  v6 = 136;
LABEL_3:
  v7 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\DownloadManagerBitsCallbackHandler.cpp",
    (const char *)0x80070057LL,
    v22);
  return v7;
}

```

## disassembly

```asm
0x180102720  mov     [rsp-8+arg_18], rbx
0x180102725  push    rbp
0x180102726  push    rsi
0x180102727  push    rdi
0x180102728  push    r14
0x18010272a  push    r15
0x18010272c  lea     rbp, [rsp-37h]
0x180102731  sub     rsp, 0D0h
0x180102738  mov     rax, cs:__security_cookie
0x18010273f  xor     rax, rsp
0x180102742  mov     [rbp+57h+var_30], rax
0x180102746  mov     rdi, r8
0x180102749  mov     rbx, rdx
0x18010274c  mov     r14, rcx
0x18010274f  xor     r15d, r15d
0x180102752  test    rdx, rdx
0x180102755  jnz     short loc_180102779
0x180102757  mov     edx, 88h; void *
0x18010275c  mov     ebx, 80070057h
0x180102761  lea     r8, aCW1SSrcClientE_119; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x180102768  mov     r9d, ebx; char *
0x18010276b  mov     rcx, [rbp+5Fh]; this
0x18010276f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102774  jmp     loc_180102B4A
0x180102779  test    rdi, rdi
0x18010277c  jnz     short loc_180102785
0x18010277e  mov     edx, 89h
0x180102783  jmp     short loc_18010275C
0x180102785  lea     rax, aJoberrorCallba; "JobError() callback received."
0x18010278c  mov     [rsp+0F0h+var_C8], rax
0x180102791  mov     qword ptr [rsp+0F0h+var_D0], r15; int
0x180102796  xor     edx, edx
0x180102798  xor     ecx, ecx
0x18010279a  lea     r9d, [rdx+5]
0x18010279e  lea     r8d, [rdx+2]
0x1801027a2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801027a7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801027ae  movdqu  [rbp+57h+var_40], xmm0
0x1801027b3  mov     rax, [rbx]
0x1801027b6  lea     rdx, [rbp+57h+var_40]
0x1801027ba  mov     rcx, rbx
0x1801027bd  mov     rax, [rax+50h]
0x1801027c1  call    _guard_dispatch_icall
0x1801027c6  mov     esi, eax
0x1801027c8  test    eax, eax
0x1801027ca  jns     short loc_1801027EB
0x1801027cc  mov     edx, 8Eh; void *
0x1801027d1  mov     rcx, [rbp+5Fh]; this
0x1801027d5  mov     r9d, esi; char *
0x1801027d8  lea     r8, aCW1SSrcClientE_119; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1801027df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801027e4  mov     eax, esi
0x1801027e6  jmp     loc_180102B4C
0x1801027eb  mov     [rbp+57h+var_B0], 4
0x1801027f2  mov     rax, [rbx]
0x1801027f5  lea     rdx, [rbp+57h+var_B0]
0x1801027f9  mov     rcx, rbx
0x1801027fc  mov     rax, [rax+70h]
0x180102800  call    _guard_dispatch_icall
0x180102805  mov     esi, eax
0x180102807  test    eax, eax
0x180102809  jns     short loc_180102812
0x18010280b  mov     edx, 91h
0x180102810  jmp     short loc_1801027D1
0x180102812  mov     [rbp+57h+var_B8], r15d
0x180102816  mov     [rbp+57h+var_B4], r15d
0x18010281a  mov     rax, [rdi]
0x18010281d  lea     r8, [rbp+57h+var_B4]
0x180102821  lea     rdx, [rbp+57h+var_B8]
0x180102825  mov     rcx, rdi
0x180102828  mov     rax, [rax+18h]
0x18010282c  call    _guard_dispatch_icall
0x180102831  mov     esi, eax
0x180102833  test    eax, eax
0x180102835  jns     short loc_18010283E
0x180102837  mov     edx, 95h
0x18010283c  jmp     short loc_1801027D1
0x18010283e  xorps   xmm0, xmm0
0x180102841  movups  [rbp+57h+var_98], xmm0
0x180102845  xorps   xmm1, xmm1
0x180102848  movdqu  xmmword ptr [rbp+57h+pv], xmm1
0x18010284d  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x180102852  mov     eax, [rbp+57h+var_B8]
0x180102855  mov     dword ptr [rbp+57h+var_98+4], eax
0x180102858  mov     eax, [rbp+57h+var_B4]
0x18010285b  mov     dword ptr [rbp+57h+var_98+8], eax
0x18010285e  mov     esi, 1
0x180102863  mov     dword ptr [rbp+57h+var_98], esi
0x180102866  mov     [rbp+57h+var_68], r15
0x18010286a  mov     rax, [rbx]
0x18010286d  lea     r8, [rbp+57h+var_68]
0x180102871  lea     rdx, _GUID_18995a26_bf59_4abe_9f8b_d5092d5a2405
0x180102878  mov     rcx, rbx
0x18010287b  mov     rax, [rax]
0x18010287e  call    _guard_dispatch_icall
0x180102883  test    eax, eax
0x180102885  js      short loc_1801028E8
0x180102887  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18010288b  call    cs:__imp_VariantInit
0x180102891  nop
0x180102892  mov     rcx, [rbp+57h+var_68]
0x180102896  mov     rax, [rcx]
0x180102899  lea     r8, [rbp+57h+pvarg]
0x18010289d  xor     edx, edx
0x18010289f  mov     rax, [rax+20h]
0x1801028a3  call    _guard_dispatch_icall
0x1801028a8  mov     ebx, eax
0x1801028aa  test    eax, eax
0x1801028ac  jns     short loc_1801028D6
0x1801028ae  mov     rcx, [rbp+5Fh]; this
0x1801028b2  mov     r9d, eax; char *
0x1801028b5  lea     r8, aCW1SSrcClientE_119; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1801028bc  mov     edx, 0A0h; void *
0x1801028c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801028c6  nop
0x1801028c7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801028cb  call    cs:__imp_VariantClear
0x1801028d1  jmp     loc_180102B2B
0x1801028d6  mov     eax, dword ptr [rbp+57h+pvarg+8]
0x1801028d9  mov     dword ptr [rbp+57h+var_98+0Ch], eax
0x1801028dc  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801028e0  call    cs:__imp_VariantClear
0x1801028e6  jmp     short loc_1801028EC
0x1801028e8  mov     dword ptr [rbp+57h+var_98+0Ch], r15d
0x1801028ec  mov     rax, [rdi]
0x1801028ef  mov     [rbp+57h+var_C0], r15
0x1801028f3  lea     rdx, [rbp+57h+var_C0]
0x1801028f7  mov     rcx, rdi
0x1801028fa  mov     rax, [rax+20h]
0x1801028fe  call    _guard_dispatch_icall
0x180102903  test    eax, eax
0x180102905  js      loc_180102A56
0x18010290b  mov     rbx, [rbp+57h+var_C0]
0x18010290f  mov     rax, [rbx]
0x180102912  mov     rdi, [rax+18h]
0x180102916  mov     rcx, [rbp+57h+pv+8]; pv
0x18010291a  test    rcx, rcx
0x18010291d  jz      short loc_180102929
0x18010291f  call    cs:__imp_CoTaskMemFree
0x180102925  mov     [rbp+57h+pv+8], r15
0x180102929  lea     rdx, [rbp+57h+pv+8]
0x18010292d  mov     rcx, rbx
0x180102930  mov     rax, rdi
0x180102933  call    _guard_dispatch_icall
0x180102938  test    eax, eax
0x18010293a  jns     short loc_18010294F
0x18010293c  mov     rcx, [rbp+57h+pv+8]; pv
0x180102940  test    rcx, rcx
0x180102943  jz      short loc_18010294B
0x180102945  call    cs:__imp_CoTaskMemFree
0x18010294b  mov     [rbp+57h+pv+8], r15
0x18010294f  mov     rbx, [rbp+57h+var_C0]
0x180102953  mov     rax, [rbx]
0x180102956  mov     rdi, [rax+20h]
0x18010295a  mov     rcx, [rbp+57h+pv]; pv
0x18010295e  test    rcx, rcx
0x180102961  jz      short loc_18010296D
0x180102963  call    cs:__imp_CoTaskMemFree
0x180102969  mov     [rbp+57h+pv], r15
0x18010296d  lea     rdx, [rbp+57h+pv]
0x180102971  mov     rcx, rbx
0x180102974  mov     rax, rdi
0x180102977  call    _guard_dispatch_icall
0x18010297c  mov     rcx, [rbp+57h+pv]; pv
0x180102980  test    eax, eax
0x180102982  js      short loc_18010298F
0x180102984  test    rcx, rcx
0x180102987  jz      short loc_18010299A
0x180102989  cmp     [rcx], r15w
0x18010298d  jnz     short loc_18010299E
0x18010298f  test    rcx, rcx
0x180102992  jz      short loc_18010299A
0x180102994  call    cs:__imp_CoTaskMemFree
0x18010299a  mov     [rbp+57h+pv], r15
0x18010299e  mov     [rbp+57h+var_A0], r15
0x1801029a2  mov     rcx, [rbp+57h+var_C0]
0x1801029a6  mov     rax, [rcx]
0x1801029a9  lea     r8, [rbp+57h+var_A0]
0x1801029ad  lea     rdx, _GUID_85c1657f_dafc_40e8_8834_df18ea25717e
0x1801029b4  mov     rax, [rax]
0x1801029b7  call    _guard_dispatch_icall
0x1801029bc  test    eax, eax
0x1801029be  js      short loc_1801029F5
0x1801029c0  mov     qword ptr [rbp+57h+pvarg], r15
0x1801029c4  mov     rcx, [rbp+57h+var_A0]
0x1801029c8  mov     rax, [rcx]
0x1801029cb  lea     r8, [rbp+57h+pvarg]
0x1801029cf  mov     edx, esi
0x1801029d1  mov     rax, [rax+70h]
0x1801029d5  call    _guard_dispatch_icall
0x1801029da  test    eax, eax
0x1801029dc  js      short loc_1801029F5
0x1801029de  mov     rbx, qword ptr [rbp+57h+pvarg]
0x1801029e2  mov     rcx, [rbp+57h+var_78]; pv
0x1801029e6  test    rcx, rcx
0x1801029e9  jz      short loc_1801029F1
0x1801029eb  call    cs:__imp_CoTaskMemFree
0x1801029f1  mov     [rbp+57h+var_78], rbx
0x1801029f5  mov     [rbp+57h+var_A8], r15
0x1801029f9  mov     rcx, [rbp+57h+var_C0]
0x1801029fd  mov     rax, [rcx]
0x180102a00  lea     r8, [rbp+57h+var_A8]
0x180102a04  lea     rdx, _GUID_b76b9699_e99e_4101_803f_a20e325d93e2
0x180102a0b  mov     rax, [rax]
0x180102a0e  call    _guard_dispatch_icall
0x180102a13  mov     rcx, [rbp+57h+var_78+8]; pv
0x180102a17  test    eax, eax
0x180102a19  jns     short loc_180102A98
0x180102a1b  test    rcx, rcx
0x180102a1e  jz      short loc_180102A26
0x180102a20  call    cs:__imp_CoTaskMemFree
0x180102a26  mov     [rbp+57h+var_78+8], r15
0x180102a2a  mov     rcx, [rbp+57h+var_A8]
0x180102a2e  test    rcx, rcx
0x180102a31  jz      short loc_180102A40
0x180102a33  mov     rax, [rcx]
0x180102a36  mov     rax, [rax+10h]
0x180102a3a  call    _guard_dispatch_icall
0x180102a3f  nop
0x180102a40  mov     rcx, [rbp+57h+var_A0]
0x180102a44  test    rcx, rcx
0x180102a47  jz      short loc_180102A56
0x180102a49  mov     rax, [rcx]
0x180102a4c  mov     rax, [rax+10h]
0x180102a50  call    _guard_dispatch_icall
0x180102a55  nop
0x180102a56  movaps  xmm0, [rbp+57h+var_40]
0x180102a5a  movdqa  xmmword ptr [rbp+57h+pvarg], xmm0
0x180102a5f  lea     r9, [rbp+57h+var_98]; struct tagDownloadJobError *
0x180102a63  mov     r8d, [rbp+57h+var_B0]; enum BG_JOB_STATE
0x180102a67  lea     rdx, [rbp+57h+pvarg]; struct _GUID
0x180102a6b  mov     rcx, [r14+8]; this
0x180102a6f  call    ?JobError@CDownloadManagerCallbackHandler@@QEAAJU_GUID@@W4BG_JOB_STATE@@PEAUtagDownloadJobError@@@Z; CDownloadManagerCallbackHandler::JobError(_GUID,BG_JOB_STATE,tagDownloadJobError *)
0x180102a74  mov     ebx, eax
0x180102a76  test    eax, eax
0x180102a78  jns     loc_180102B12
0x180102a7e  mov     rcx, [rbp+5Fh]; this
0x180102a82  mov     r9d, eax; char *
0x180102a85  lea     r8, aCW1SSrcClientE_119; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x180102a8c  mov     edx, 0D2h; void *
0x180102a91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102a96  jmp     short loc_180102B15
0x180102a98  mov     rbx, [rbp+57h+var_A8]
0x180102a9c  mov     rax, [rbx]
0x180102a9f  mov     rdi, [rax+18h]
0x180102aa3  test    rcx, rcx
0x180102aa6  jz      short loc_180102AB2
0x180102aa8  call    cs:__imp_CoTaskMemFree
0x180102aae  mov     [rbp+57h+var_78+8], r15
0x180102ab2  lea     rdx, [rbp+57h+var_78+8]
0x180102ab6  mov     rcx, rbx
0x180102ab9  mov     rax, rdi
0x180102abc  call    _guard_dispatch_icall
0x180102ac1  mov     ebx, eax
0x180102ac3  test    eax, eax
0x180102ac5  jns     loc_180102A2A
0x180102acb  mov     rcx, [rbp+5Fh]; this
0x180102acf  mov     r9d, eax; char *
0x180102ad2  lea     r8, aCW1SSrcClientE_119; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x180102ad9  mov     edx, 0CEh; void *
0x180102ade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102ae3  nop
0x180102ae4  mov     rcx, [rbp+57h+var_A8]
0x180102ae8  test    rcx, rcx
0x180102aeb  jz      short loc_180102AFA
0x180102aed  mov     rax, [rcx]
0x180102af0  mov     rax, [rax+10h]
0x180102af4  call    _guard_dispatch_icall
0x180102af9  nop
0x180102afa  mov     rcx, [rbp+57h+var_A0]
0x180102afe  test    rcx, rcx
0x180102b01  jz      short loc_180102B10
0x180102b03  mov     rax, [rcx]
0x180102b06  mov     rax, [rax+10h]
0x180102b0a  call    _guard_dispatch_icall
0x180102b0f  nop
0x180102b10  jmp     short loc_180102B15
0x180102b12  mov     ebx, r15d
0x180102b15  mov     rcx, [rbp+57h+var_C0]
0x180102b19  test    rcx, rcx
0x180102b1c  jz      short loc_180102B2B
0x180102b1e  mov     rax, [rcx]
0x180102b21  mov     rax, [rax+10h]
0x180102b25  call    _guard_dispatch_icall
0x180102b2a  nop
0x180102b2b  mov     rcx, [rbp+57h+var_68]
0x180102b2f  test    rcx, rcx
0x180102b32  jz      short loc_180102B41
0x180102b34  mov     rdx, [rcx]
0x180102b37  mov     rax, [rdx+10h]
0x180102b3b  call    _guard_dispatch_icall
0x180102b40  nop
0x180102b41  lea     rcx, [rbp+57h+var_98]; this
0x180102b45  call    ??1tagDownloadJobError@@QEAA@XZ; tagDownloadJobError::~tagDownloadJobError(void)
0x180102b4a  mov     eax, ebx
0x180102b4c  mov     rcx, [rbp+57h+var_30]
0x180102b50  xor     rcx, rsp; StackCookie
0x180102b53  call    __security_check_cookie
0x180102b58  mov     rbx, [rsp+0F0h+arg_18]
0x180102b60  add     rsp, 0D0h
  ... truncated ...
```
