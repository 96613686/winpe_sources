# AuditLogRecordOneXResult(ulong,AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *,_DOT11_SSID *,ushort *,_LUID,uchar (*)[6],uchar (*)[6],_GUID *,ulong,ulong,ulong,ushort *,ulong)

- ea: `0x180027fbc`
- end: `0x18002847a`
- name: `?AuditLogRecordOneXResult@@YAKKPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@PEAU_DOT11_SSID@@PEAGU_LUID@@PEAY05E4PEAU_GUID@@KKK2K@Z`
- size: `1214`
- prototype: `unsigned int __fastcall(unsigned int, struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *, struct _DOT11_SSID *, unsigned __int16 *, struct _LUID, unsigned __int8 (*)[6], unsigned __int8 (*)[6], struct _GUID *, unsigned int, unsigned int, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029660`

## callees

- `0x18000431c`
- `0x18000892c`
- `0x180008998`
- `0x180016b1c`
- `0x180027fbc`
- `0x180028480`
- `0x180028574`
- `0x180043a30`
- `0x18004456c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002841b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002841b`
- `AUTHZ!AuthziLogAuditEvent` at `0x18002839d`
- `AUTHZ!AuthziLogAuditEvent` at `0x18002839d`
- `AUTHZ!AuthziInitializeAuditParams` at `0x1800282d3`
- `AUTHZ!AuthziInitializeAuditParams` at `0x1800282d3`
- `AUTHZ!AuthzFreeAuditEvent` at `0x1800283fc`
- `AUTHZ!AuthzFreeAuditEvent` at `0x1800283fc`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x180028359`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x180028359`

## string_xrefs

- `0x1800281d9`: `Security`

## pseudocode

```c
__int64 __fastcall AuditLogRecordOneXResult(
        unsigned int a1,
        struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *a2,
        struct _DOT11_SSID *a3,
        unsigned __int16 *a4,
        struct _LUID a5,
        unsigned __int8 (*a6)[6],
        unsigned __int8 (*a7)[6],
        struct _GUID *a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11,
        unsigned __int16 *a12,
        unsigned int a13)
{
  int *v13; // rsi
  unsigned int v18; // edx
  DWORD LastError; // eax
  unsigned int v20; // edx
  DWORD v21; // ebx
  PVOID *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  int v27; // [rsp+20h] [rbp-150h]
  int v28; // [rsp+F0h] [rbp-80h] BYREF
  AUTHZ_AUDIT_EVENT_HANDLE hAuditEvent; // [rsp+F8h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+100h] [rbp-70h] BYREF
  struct _GUID *v31; // [rsp+108h] [rbp-68h]
  __int128 v32; // [rsp+110h] [rbp-60h] BYREF
  _BYTE *v33; // [rsp+120h] [rbp-50h]
  _BYTE v34[512]; // [rsp+130h] [rbp-40h] BYREF
  unsigned __int16 v35[8]; // [rsp+330h] [rbp+1C0h] BYREF
  __int128 v36; // [rsp+340h] [rbp+1D0h]
  int v37; // [rsp+350h] [rbp+1E0h]
  unsigned __int16 v38[8]; // [rsp+358h] [rbp+1E8h] BYREF
  __int128 v39; // [rsp+368h] [rbp+1F8h]
  int v40; // [rsp+378h] [rbp+208h]
  _BYTE v41[64]; // [rsp+380h] [rbp+210h] BYREF
  __int16 v42; // [rsp+3C0h] [rbp+250h]
  _WORD v43[256]; // [rsp+3D0h] [rbp+260h] BYREF

  v13 = (int *)a12;
  v31 = a8;
  v40 = 0;
  v37 = 0;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  memset_0(v41, 0, 0x42u);
  memset_0(v43, 0, sizeof(v43));
  hAuditEvent = 0;
  hMem = 0;
  memset_0(v34, 0, sizeof(v34));
  v32 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_0b5270da64a83b58b4f6bf593b59f41d_Traceguids);
  v28 = 33;
  WlanSsidToWideString(a3, v41, &v28);
  v42 = 0;
  LastError = MacAddressToString(a6, v18, v38);
  v21 = LastError;
  if ( LastError )
  {
    v22 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v23 = 15;
LABEL_33:
      WPP_SF_d(v22[7], v23, WPP_0b5270da64a83b58b4f6bf593b59f41d_Traceguids, LastError);
LABEL_34:
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    LastError = MacAddressToString(a7, v20, v35);
    v21 = LastError;
    if ( LastError )
    {
      v22 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v23 = 16;
        goto LABEL_33;
      }
    }
    else
    {
      v21 = ReasonCodeToString(v24, a9, v25, v43);
      if ( v21 )
      {
        v43[0] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_0b5270da64a83b58b4f6bf593b59f41d_Traceguids, a9, v21);
      }
      v33 = v34;
      if ( !a12 )
        v13 = &dword_18009F91C;
      LOWORD(v27) = 12;
      if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _QWORD, _DWORD, _DWORD))AuthziInitializeAuditParams)(
                           a1,
                           &v32,
                           &hMem,
                           L"Security",
                           v27,
                           2,
                           v41,
                           2,
                           a4,
                           6,
                           a5,
                           2,
                           v38,
                           2,
                           v35,
                           9,
                           v31,
                           3,
                           a9,
                           2,
                           v43,
                           3,
                           a10,
                           3,
                           a11,
                           2,
                           v13,
                           3,
                           a13)
        || (LastError = GetLastError(), (v21 = LastError) == 0) )
      {
        if ( (unsigned int)AuthziInitializeAuditEvent(
                             0,
                             0,
                             a2,
                             &v32,
                             0,
                             -1,
                             &byte_18009AFB8,
                             &byte_18009AFB8,
                             &byte_18009AFB8,
                             &byte_18009AFB8,
                             &hAuditEvent)
          || (LastError = GetLastError(), (v21 = LastError) == 0) )
        {
          if ( (unsigned int)AuthziLogAuditEvent(0, hAuditEvent, 0) )
            goto LABEL_34;
          LastError = GetLastError();
          v21 = LastError;
          if ( !LastError )
            goto LABEL_34;
          v22 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            v23 = 20;
            goto LABEL_33;
          }
        }
        else
        {
          v22 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            v23 = 19;
            goto LABEL_33;
          }
        }
      }
      else
      {
        v22 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v23 = 18;
          goto LABEL_33;
        }
      }
    }
  }
  if ( hAuditEvent )
  {
    AuthzFreeAuditEvent(hAuditEvent);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v22 != &WPP_GLOBAL_Control && (*((_DWORD *)v22 + 17) & 0x100) != 0 )
    WPP_SF_d(v22[7], 21, WPP_0b5270da64a83b58b4f6bf593b59f41d_Traceguids, v21);
  return v21;
}

```

## disassembly

```asm
0x180027fbc  push    rbp
0x180027fbe  push    rbx
0x180027fbf  push    rsi
0x180027fc0  push    rdi
0x180027fc1  push    r12
0x180027fc3  push    r13
0x180027fc5  push    r14
0x180027fc7  push    r15
0x180027fc9  lea     rbp, [rsp-478h]
0x180027fd1  sub     rsp, 5E8h
0x180027fd8  mov     rax, cs:__security_cookie
0x180027fdf  xor     rax, rsp
0x180027fe2  mov     [rbp+4B0h+var_50], rax
0x180027fe9  mov     rax, [rbp+4B0h+arg_38]
0x180027ff0  xorps   xmm0, xmm0
0x180027ff3  mov     rsi, [rbp+4B0h+arg_58]
0x180027ffa  xorps   xmm1, xmm1
0x180027ffd  mov     r14, [rbp+4B0h+arg_28]
0x180028004  mov     rbx, r8
0x180028007  mov     rdi, [rbp+4B0h+arg_30]
0x18002800e  mov     r15, rdx
0x180028011  mov     [rbp+4B0h+var_518], rax
0x180028015  mov     r12d, ecx
0x180028018  xor     eax, eax
0x18002801a  lea     rcx, [rbp+4B0h+var_2A0]; void *
0x180028021  xor     edx, edx; Val
0x180028023  mov     [rbp+4B0h+var_2A8], eax
0x180028029  mov     r13, r9
0x18002802c  mov     [rbp+4B0h+var_2D0], eax
0x180028032  movups  xmmword ptr [rbp+4B0h+var_2C8], xmm0
0x180028039  lea     r8d, [rax+42h]; Size
0x18002803d  movups  [rbp+4B0h+var_2B8], xmm0
0x180028044  movups  xmmword ptr [rbp+4B0h+var_2F0], xmm1
0x18002804b  movups  [rbp+4B0h+var_2E0], xmm1
0x180028052  call    memset_0
0x180028057  xor     edx, edx; Val
0x180028059  lea     rcx, [rbp+4B0h+var_250]; void *
0x180028060  mov     r8d, 200h; Size
0x180028066  call    memset_0
0x18002806b  xor     edx, edx; Val
0x18002806d  mov     [rbp+4B0h+hAuditEvent], 0
0x180028075  mov     r8d, 200h; Size
0x18002807b  mov     [rbp+4B0h+hMem], 0
0x180028083  lea     rcx, [rbp+4B0h+var_4F0]; void *
0x180028087  call    memset_0
0x18002808c  xorps   xmm0, xmm0
0x18002808f  xor     eax, eax
0x180028091  movups  [rbp+4B0h+var_510], xmm0
0x180028095  mov     [rbp+4B0h+var_500], rax
0x180028099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280a0  lea     rax, WPP_GLOBAL_Control
0x1800280a7  cmp     rcx, rax
0x1800280aa  jz      short loc_1800280CA
0x1800280ac  test    dword ptr [rcx+44h], 100h
0x1800280b3  jz      short loc_1800280CA
0x1800280b5  mov     rcx, [rcx+38h]
0x1800280b9  lea     r8, WPP_0b5270da64a83b58b4f6bf593b59f41d_Traceguids
0x1800280c0  mov     edx, 0Eh
0x1800280c5  call    WPP_SF_
0x1800280ca  lea     r8, [rbp+4B0h+var_530]
0x1800280ce  mov     [rbp+4B0h+var_530], 21h ; '!'
0x1800280d5  lea     rdx, [rbp+4B0h+var_2A0]
0x1800280dc  mov     rcx, rbx
0x1800280df  call    WlanSsidToWideString
0x1800280e4  xor     eax, eax
0x1800280e6  lea     r8, [rbp+4B0h+var_2C8]; unsigned __int16 *
0x1800280ed  mov     rcx, r14; unsigned __int8 (*)[6]
0x1800280f0  mov     [rbp+4B0h+var_260], ax
0x1800280f7  call    ?MacAddressToString@@YAKPEAY05EKPEAG@Z; MacAddressToString(uchar (*)[6],ulong,ushort *)
0x1800280fc  mov     ebx, eax
0x1800280fe  test    eax, eax
0x180028100  jz      short loc_18002812D
0x180028102  mov     rcx, cs:WPP_GLOBAL_Control
0x180028109  lea     r14, WPP_GLOBAL_Control
0x180028110  cmp     rcx, r14
0x180028113  jz      loc_1800283F0
0x180028119  test    byte ptr [rcx+44h], 1
0x18002811d  jz      loc_1800283F0
0x180028123  mov     edx, 0Fh
0x180028128  jmp     loc_1800283D6
0x18002812d  lea     r8, [rbp+4B0h+var_2F0]; unsigned __int16 *
0x180028134  mov     rcx, rdi; unsigned __int8 (*)[6]
0x180028137  call    ?MacAddressToString@@YAKPEAY05EKPEAG@Z; MacAddressToString(uchar (*)[6],ulong,ushort *)
0x18002813c  mov     ebx, eax
0x18002813e  test    eax, eax
0x180028140  jz      short loc_18002816D
0x180028142  mov     rcx, cs:WPP_GLOBAL_Control
0x180028149  lea     r14, WPP_GLOBAL_Control
0x180028150  cmp     rcx, r14
0x180028153  jz      loc_1800283F0
0x180028159  test    byte ptr [rcx+44h], 1
0x18002815d  jz      loc_1800283F0
0x180028163  mov     edx, 10h
0x180028168  jmp     loc_1800283D6
0x18002816d  mov     edi, [rbp+4B0h+arg_40]
0x180028173  lea     r9, [rbp+4B0h+var_250]
0x18002817a  mov     edx, edi
0x18002817c  call    ReasonCodeToString
0x180028181  mov     ebx, eax
0x180028183  test    eax, eax
0x180028185  jz      short loc_1800281C5
0x180028187  xor     eax, eax
0x180028189  mov     [rbp+4B0h+var_250], ax
0x180028190  mov     rcx, cs:WPP_GLOBAL_Control
0x180028197  lea     r14, WPP_GLOBAL_Control
0x18002819e  cmp     rcx, r14
0x1800281a1  jz      short loc_1800281CC
0x1800281a3  test    byte ptr [rcx+44h], 1
0x1800281a7  jz      short loc_1800281CC
0x1800281a9  mov     rcx, [rcx+38h]
0x1800281ad  lea     edx, [rax+11h]
0x1800281b0  mov     r9d, edi
0x1800281b3  mov     dword ptr [rsp+620h+var_600], ebx
0x1800281b7  lea     r8, WPP_0b5270da64a83b58b4f6bf593b59f41d_Traceguids
0x1800281be  call    WPP_SF_dd
0x1800281c3  jmp     short loc_1800281CC
0x1800281c5  lea     r14, WPP_GLOBAL_Control
0x1800281cc  mov     ecx, 3
0x1800281d1  lea     rax, [rbp+4B0h+var_4F0]
0x1800281d5  mov     [rbp+4B0h+var_500], rax
0x1800281d9  lea     r9, aSecurity; "Security"
0x1800281e0  lea     rax, dword_18009F91C
0x1800281e7  test    rsi, rsi
0x1800281ea  lea     r8, [rbp+4B0h+hMem]
0x1800281ee  cmovz   rsi, rax
0x1800281f2  lea     edx, [rcx-1]
0x1800281f5  mov     eax, [rbp+4B0h+arg_60]
0x1800281fb  mov     [rsp+620h+var_540], eax
0x180028202  mov     eax, [rbp+4B0h+arg_50]
0x180028208  mov     [rsp+620h+var_548], ecx
0x18002820f  mov     [rsp+620h+var_550], rsi
0x180028217  mov     [rsp+620h+var_558], edx
0x18002821e  mov     [rsp+620h+var_560], eax
0x180028225  mov     eax, [rbp+4B0h+arg_48]
0x18002822b  mov     [rsp+620h+var_568], ecx
0x180028232  mov     [rsp+620h+var_570], eax
0x180028239  lea     rax, [rbp+4B0h+var_250]
0x180028240  mov     [rsp+620h+var_578], ecx
0x180028247  mov     [rsp+620h+var_580], rax
0x18002824f  mov     rax, [rbp+4B0h+var_518]
0x180028253  mov     [rsp+620h+var_588], edx
0x18002825a  mov     [rsp+620h+var_590], edi
0x180028261  mov     [rsp+620h+var_598], ecx
0x180028268  mov     ecx, r12d
0x18002826b  mov     [rsp+620h+var_5A0], rax
0x180028273  lea     rax, [rbp+4B0h+var_2F0]
0x18002827a  mov     [rsp+620h+var_5A8], 9
0x180028282  mov     [rsp+620h+var_5B0], rax
0x180028287  lea     rax, [rbp+4B0h+var_2C8]
0x18002828e  mov     [rsp+620h+var_5B8], edx
0x180028292  mov     [rsp+620h+var_5C0], rax
0x180028297  mov     rax, qword ptr [rbp+4B0h+arg_20.LowPart]
0x18002829e  mov     [rsp+620h+var_5C8], edx
0x1800282a2  mov     [rsp+620h+var_5D0], rax
0x1800282a7  lea     rax, [rbp+4B0h+var_2A0]
0x1800282ae  mov     dword ptr [rsp+620h+var_5D8], 6
0x1800282b6  mov     [rsp+620h+var_5E0], r13
0x1800282bb  mov     dword ptr [rsp+620h+var_5E8], edx
0x1800282bf  mov     [rsp+620h+var_5F0], rax
0x1800282c4  mov     [rsp+620h+var_5F8], edx
0x1800282c8  lea     rdx, [rbp+4B0h+var_510]
0x1800282cc  mov     word ptr [rsp+620h+var_600], 0Ch
0x1800282d3  call    cs:__imp_AuthziInitializeAuditParams
0x1800282da  nop     dword ptr [rax+rax+00h]
0x1800282df  test    eax, eax
0x1800282e1  jnz     short loc_180028319
0x1800282e3  call    cs:__imp_GetLastError
0x1800282ea  nop     dword ptr [rax+rax+00h]
0x1800282ef  mov     ebx, eax
0x1800282f1  test    eax, eax
0x1800282f3  jz      short loc_180028319
0x1800282f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282fc  cmp     rcx, r14
0x1800282ff  jz      loc_1800283F0
0x180028305  test    byte ptr [rcx+44h], 1
0x180028309  jz      loc_1800283F0
0x18002830f  mov     edx, 12h
0x180028314  jmp     loc_1800283D6
0x180028319  lea     rax, [rbp+4B0h+hAuditEvent]
0x18002831d  mov     r8, r15
0x180028320  mov     [rsp+620h+var_5D0], rax
0x180028325  lea     r9, [rbp+4B0h+var_510]
0x180028329  lea     rax, byte_18009AFB8
0x180028330  xor     edx, edx
0x180028332  mov     [rsp+620h+var_5D8], rax
0x180028337  xor     ecx, ecx
0x180028339  mov     [rsp+620h+var_5E0], rax
0x18002833e  mov     [rsp+620h+var_5E8], rax
0x180028343  mov     [rsp+620h+var_5F0], rax
0x180028348  mov     [rsp+620h+var_5F8], 0FFFFFFFFh
0x180028350  mov     [rsp+620h+var_600], 0
0x180028359  call    cs:__imp_AuthziInitializeAuditEvent
0x180028360  nop     dword ptr [rax+rax+00h]
0x180028365  test    eax, eax
0x180028367  jnz     short loc_180028394
0x180028369  call    cs:__imp_GetLastError
0x180028370  nop     dword ptr [rax+rax+00h]
0x180028375  mov     ebx, eax
0x180028377  test    eax, eax
0x180028379  jz      short loc_180028394
0x18002837b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028382  cmp     rcx, r14
0x180028385  jz      short loc_1800283F0
0x180028387  test    byte ptr [rcx+44h], 1
0x18002838b  jz      short loc_1800283F0
0x18002838d  mov     edx, 13h
0x180028392  jmp     short loc_1800283D6
0x180028394  mov     rdx, [rbp+4B0h+hAuditEvent]
0x180028398  xor     r8d, r8d
0x18002839b  xor     ecx, ecx
0x18002839d  call    cs:__imp_AuthziLogAuditEvent
0x1800283a4  nop     dword ptr [rax+rax+00h]
0x1800283a9  test    eax, eax
0x1800283ab  jnz     short loc_1800283E9
0x1800283ad  call    cs:__imp_GetLastError
0x1800283b4  nop     dword ptr [rax+rax+00h]
0x1800283b9  mov     ebx, eax
0x1800283bb  test    eax, eax
0x1800283bd  jz      short loc_1800283E9
0x1800283bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283c6  cmp     rcx, r14
0x1800283c9  jz      short loc_1800283F0
0x1800283cb  test    byte ptr [rcx+44h], 1
0x1800283cf  jz      short loc_1800283F0
0x1800283d1  mov     edx, 14h
0x1800283d6  mov     rcx, [rcx+38h]
0x1800283da  lea     r8, WPP_0b5270da64a83b58b4f6bf593b59f41d_Traceguids
0x1800283e1  mov     r9d, eax
0x1800283e4  call    WPP_SF_d
0x1800283e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283f0  mov     rax, [rbp+4B0h+hAuditEvent]
0x1800283f4  test    rax, rax
0x1800283f7  jz      short loc_18002840F
0x1800283f9  mov     rcx, rax; hAuditEvent
0x1800283fc  call    cs:__imp_AuthzFreeAuditEvent
0x180028403  nop     dword ptr [rax+rax+00h]
0x180028408  mov     rcx, cs:WPP_GLOBAL_Control
0x18002840f  mov     rax, [rbp+4B0h+hMem]
0x180028413  test    rax, rax
0x180028416  jz      short loc_18002842E
0x180028418  mov     rcx, rax; hMem
0x18002841b  call    cs:__imp_LocalFree
0x180028422  nop     dword ptr [rax+rax+00h]
0x180028427  mov     rcx, cs:WPP_GLOBAL_Control
0x18002842e  cmp     rcx, r14
0x180028431  jz      short loc_180028454
0x180028433  test    dword ptr [rcx+44h], 100h
0x18002843a  jz      short loc_180028454
0x18002843c  mov     rcx, [rcx+38h]
0x180028440  lea     r8, WPP_0b5270da64a83b58b4f6bf593b59f41d_Traceguids
0x180028447  mov     edx, 15h
0x18002844c  mov     r9d, ebx
0x18002844f  call    WPP_SF_d
0x180028454  mov     eax, ebx
0x180028456  mov     rcx, [rbp+4B0h+var_50]
0x18002845d  xor     rcx, rsp; StackCookie
0x180028460  call    __security_check_cookie
0x180028465  add     rsp, 5E8h
0x18002846c  pop     r15
0x18002846e  pop     r14
0x180028470  pop     r13
0x180028472  pop     r12
0x180028474  pop     rdi
0x180028475  pop     rsi
0x180028476  pop     rbx
0x180028477  pop     rbp
0x180028478  retn
```
