# GetCertifictateContextFromHash

- ea: `0x180009364`
- end: `0x1800095f1`
- name: `GetCertifictateContextFromHash`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002ccc4`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x180009364`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000950b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000950b`
- `CRYPT32!CertOpenStore` at `0x18000946a`
- `CRYPT32!CertOpenStore` at `0x18000946a`
- `CRYPT32!CertFindCertificateInStore` at `0x1800094fd`
- `CRYPT32!CertFindCertificateInStore` at `0x1800094fd`
- `CRYPT32!CertFreeCertificateContext` at `0x18000956b`
- `CRYPT32!CertFreeCertificateContext` at `0x18000956b`
- `CRYPT32!CertCloseStore` at `0x180009582`
- `CRYPT32!CertCloseStore` at `0x180009582`

## string_xrefs

- `0x18000948d`: `GetCertifictateContextFromHash : CertOpenStore failed and returned %d`

## pseudocode

```c
__int64 __fastcall GetCertifictateContextFromHash(__int64 a1, PCCERT_CONTEXT *a2)
{
  HCERTSTORE v4; // rax
  void *v5; // rdi
  DWORD v6; // eax
  const CERT_CONTEXT *v7; // rbx
  PCCERT_CONTEXT CertificateInStore; // rax
  DWORD LastError; // eax
  unsigned int v10; // ebx
  unsigned int v12; // [rsp+30h] [rbp-D0h] BYREF
  __int128 pvFindPara; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h]
  __int128 v16; // [rsp+60h] [rbp-A0h]
  __int64 v17; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+7Ch] [rbp-84h]
  int v20; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v21[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids);
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v12 = 0;
  pvFindPara = 0;
  v14 = 0;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  v18 = -1;
  v19 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"GetCertifictateContextFromHash",
      &v12,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  *a2 = 0;
  v4 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"ROOT");
  v5 = v4;
  if ( v4 )
  {
    LODWORD(pvFindPara) = *(_DWORD *)a1;
    *((_QWORD *)&pvFindPara + 1) = *(_QWORD *)(a1 + 8);
    CertificateInStore = CertFindCertificateInStore(v4, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
    v7 = CertificateInStore;
    if ( CertificateInStore )
    {
      *a2 = CertificateInStore;
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(
          &v20,
          L"GetCertifictateContextFromHash : CertFindCertificateInStore failed and returned %d",
          LastError);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v20);
      }
    }
  }
  else
  {
    v6 = GetLastError();
    v12 = v6;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, L"GetCertifictateContextFromHash : CertOpenStore failed and returned %d", v6);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v20);
    }
    v7 = 0;
  }
  if ( v12 && v7 )
  {
    CertFreeCertificateContext(v7);
    *a2 = 0;
  }
  if ( v5 )
    CertCloseStore(v5, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids, v12);
  }
  v10 = v12;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return v10;
}

```

## disassembly

```asm
0x180009364  mov     [rsp-8+arg_10], rbx
0x180009369  mov     [rsp-8+arg_18], rsi
0x18000936e  push    rbp
0x18000936f  push    rdi
0x180009370  push    r15
0x180009372  lea     rbp, [rsp-790h]
0x18000937a  sub     rsp, 890h
0x180009381  mov     rax, cs:__security_cookie
0x180009388  xor     rax, rsp
0x18000938b  mov     [rbp+7A0h+var_20], rax
0x180009392  mov     rsi, rdx
0x180009395  mov     rbx, rcx
0x180009398  mov     rcx, cs:WPP_GLOBAL_Control
0x18000939f  lea     r15, WPP_GLOBAL_Control
0x1800093a6  cmp     rcx, r15
0x1800093a9  jz      short loc_1800093CC
0x1800093ab  test    byte ptr [rcx+1Ch], 1
0x1800093af  jz      short loc_1800093CC
0x1800093b1  cmp     byte ptr [rcx+19h], 6
0x1800093b5  jb      short loc_1800093CC
0x1800093b7  mov     rcx, [rcx+10h]
0x1800093bb  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x1800093c2  mov     edx, 21h ; '!'
0x1800093c7  call    WPP_SF_
0x1800093cc  xor     eax, eax
0x1800093ce  lea     rcx, [rbp+7A0h+var_81C]; void *
0x1800093d2  xor     edx, edx; Val
0x1800093d4  mov     [rbp+7A0h+var_820], eax
0x1800093d7  mov     r8d, 7FCh; Size
0x1800093dd  call    memset_0
0x1800093e2  test    cs:byte_1800AA941, 8
0x1800093e9  xorps   xmm0, xmm0
0x1800093ec  xorps   xmm1, xmm1
0x1800093ef  mov     [rsp+8A0h+var_870], 0
0x1800093f7  movups  [rsp+8A0h+pvFindPara], xmm0
0x1800093fc  mov     [rsp+8A0h+var_858], 0
0x180009405  movdqu  [rsp+8A0h+var_850], xmm1
0x18000940b  mov     [rsp+8A0h+var_830], 0
0x180009414  movdqu  [rsp+8A0h+var_840], xmm0
0x18000941a  mov     [rsp+8A0h+var_828], 0FFFFFFFFh
0x180009422  mov     [rsp+8A0h+var_824], 0
0x18000942a  jz      short loc_180009449
0x18000942c  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180009433  lea     r8, [rsp+8A0h+var_870]; unsigned int *
0x180009438  lea     rdx, aGetcertifictat; "GetCertifictateContextFromHash"
0x18000943f  lea     rcx, [rsp+8A0h+var_858]; this
0x180009444  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180009449  xor     edx, edx; dwEncodingType
0x18000944b  mov     qword ptr [rsi], 0
0x180009452  lea     rax, aRoot; "ROOT"
0x180009459  mov     r9d, 28000h; dwFlags
0x18000945f  xor     r8d, r8d; hCryptProv
0x180009462  mov     [rsp+8A0h+pvPara], rax; pvPara
0x180009467  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18000946a  call    cs:__imp_CertOpenStore
0x180009470  mov     rdi, rax
0x180009473  test    rax, rax
0x180009476  jnz     short loc_1800094CB
0x180009478  call    cs:__imp_GetLastError
0x18000947e  test    cs:byte_1800AA941, 4
0x180009485  mov     [rsp+8A0h+var_870], eax
0x180009489  jz      short loc_1800094C4
0x18000948b  xor     ecx, ecx
0x18000948d  lea     rdx, aGetcertifictat_0; "GetCertifictateContextFromHash : CertOp"...
0x180009494  mov     word ptr [rbp+7A0h+var_820], cx
0x180009498  mov     r8d, eax
0x18000949b  lea     rcx, [rbp+7A0h+var_820]
0x18000949f  call    FormatRRASErrorString
0x1800094a4  test    cs:byte_1800AA941, 4
0x1800094ab  jz      short loc_1800094C4
0x1800094ad  lea     r8, [rbp+7A0h+var_820]
0x1800094b1  lea     rdx, RasVpnIkeTraceError
0x1800094b8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800094bf  call    McTemplateU0z_EventWriteTransfer
0x1800094c4  xor     ebx, ebx
0x1800094c6  jmp     loc_18000955C
0x1800094cb  mov     eax, [rbx]
0x1800094cd  mov     r9d, 10000h; dwFindType
0x1800094d3  mov     dword ptr [rsp+8A0h+pvFindPara], eax
0x1800094d7  xor     r8d, r8d; dwFindFlags
0x1800094da  mov     rax, [rbx+8]
0x1800094de  mov     rcx, rdi; hCertStore
0x1800094e1  mov     qword ptr [rsp+8A0h+pvFindPara+8], rax
0x1800094e6  lea     rax, [rsp+8A0h+pvFindPara]
0x1800094eb  mov     [rsp+8A0h+pPrevCertContext], 0; pPrevCertContext
0x1800094f4  lea     edx, [r9+1]; dwCertEncodingType
0x1800094f8  mov     [rsp+8A0h+pvPara], rax; pvFindPara
0x1800094fd  call    cs:__imp_CertFindCertificateInStore
0x180009503  mov     rbx, rax
0x180009506  test    rax, rax
0x180009509  jnz     short loc_180009559
0x18000950b  call    cs:__imp_GetLastError
0x180009511  test    cs:byte_1800AA941, 4
0x180009518  mov     [rsp+8A0h+var_870], eax
0x18000951c  jz      short loc_18000955C
0x18000951e  xor     ecx, ecx
0x180009520  lea     rdx, aGetcertifictat_1; "GetCertifictateContextFromHash : CertFi"...
0x180009527  mov     word ptr [rbp+7A0h+var_820], cx
0x18000952b  mov     r8d, eax
0x18000952e  lea     rcx, [rbp+7A0h+var_820]
0x180009532  call    FormatRRASErrorString
0x180009537  test    cs:byte_1800AA941, 4
0x18000953e  jz      short loc_18000955C
0x180009540  lea     r8, [rbp+7A0h+var_820]
0x180009544  lea     rdx, RasVpnIkeTraceError
0x18000954b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009552  call    McTemplateU0z_EventWriteTransfer
0x180009557  jmp     short loc_18000955C
0x180009559  mov     [rsi], rax
0x18000955c  cmp     [rsp+8A0h+var_870], 0
0x180009561  jz      short loc_180009578
0x180009563  test    rbx, rbx
0x180009566  jz      short loc_180009578
0x180009568  mov     rcx, rbx; pCertContext
0x18000956b  call    cs:__imp_CertFreeCertificateContext
0x180009571  mov     qword ptr [rsi], 0
0x180009578  test    rdi, rdi
0x18000957b  jz      short loc_180009588
0x18000957d  xor     edx, edx; dwFlags
0x18000957f  mov     rcx, rdi; hCertStore
0x180009582  call    cs:__imp_CertCloseStore
0x180009588  mov     rcx, cs:WPP_GLOBAL_Control
0x18000958f  cmp     rcx, r15
0x180009592  jz      short loc_1800095BA
0x180009594  test    byte ptr [rcx+1Ch], 1
0x180009598  jz      short loc_1800095BA
0x18000959a  cmp     byte ptr [rcx+19h], 6
0x18000959e  jb      short loc_1800095BA
0x1800095a0  mov     r9d, [rsp+8A0h+var_870]
0x1800095a5  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x1800095ac  mov     rcx, [rcx+10h]
0x1800095b0  mov     edx, 22h ; '"'
0x1800095b5  call    WPP_SF_d
0x1800095ba  mov     ebx, [rsp+8A0h+var_870]
0x1800095be  lea     rcx, [rsp+8A0h+var_858]; this
0x1800095c3  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800095c8  mov     eax, ebx
0x1800095ca  mov     rcx, [rbp+7A0h+var_20]
0x1800095d1  xor     rcx, rsp; StackCookie
0x1800095d4  call    __security_check_cookie
0x1800095d9  lea     r11, [rsp+8A0h+var_10]
0x1800095e1  mov     rbx, [r11+30h]
0x1800095e5  mov     rsi, [r11+38h]
0x1800095e9  mov     rsp, r11
0x1800095ec  pop     r15
0x1800095ee  pop     rdi
0x1800095ef  pop     rbp
0x1800095f0  retn
```
