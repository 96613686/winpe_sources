# VPNIKEProtocolEngine::GetRasDeviceParams(void *,_CONNECTION_ID_ &,char *)

- ea: `0x180003e80`
- end: `0x18000427d`
- name: `?GetRasDeviceParams@VPNIKEProtocolEngine@@MEAAKPEAXAEAT_CONNECTION_ID_@@PEAD@Z`
- size: `1021`
- prototype: `__int64 __fastcall(VPNIKEProtocolEngine *this, void *, union _CONNECTION_ID_ *, char *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003e80`
- `0x180007610`
- `0x180007724`
- `0x180007794`
- `0x1800077bc`
- `0x1800768d4`
- `0x180076a70`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `msvcrt!_stricmp` at `0x18000410e`
- `msvcrt!_stricmp` at `0x18000413e`
- `msvcrt!_stricmp` at `0x18000410e`
- `msvcrt!_stricmp` at `0x18000413e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000419e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000419e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004039`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004039`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000402b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004190`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000402b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004190`

## string_xrefs

- `0x180003f66`: `VPNIKEProtocolEngine::GetRasDeviceParams`

## pseudocode

```c
__int64 __fastcall VPNIKEProtocolEngine::GetRasDeviceParams(
        VPNIKEProtocolEngine *this,
        void *a2,
        union _CONNECTION_ID_ *a3,
        char *a4)
{
  void (*v7)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v8; // edi
  int v9; // eax
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v12; // rax
  unsigned int *v13; // rsi
  unsigned int v14; // r14d
  unsigned int v15; // edi
  STRSAFE_PCNZCH *i; // rbx
  bool v17; // zf
  HANDLE v18; // rax
  struct _GUID *v20; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v21; // [rsp+28h] [rbp-D8h]
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD dwBytes[3]; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v24; // [rsp+50h] [rbp-B0h]
  __int128 v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+7Ch] [rbp-84h]
  struct _GUID v29; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+90h] [rbp-70h] BYREF
  __int128 v31; // [rsp+94h] [rbp-6Ch]
  __int128 v32; // [rsp+A4h] [rbp-5Ch]
  int v33; // [rsp+B4h] [rbp-4Ch]
  int v34; // [rsp+C0h] [rbp-40h] BYREF
  char v35[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
  }
  v22 = 0;
  memset(dwBytes, 0, sizeof(dwBytes));
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v29 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = -1;
  v28 = 0;
  v8 = 8;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&dwBytes[1],
      L"VPNIKEProtocolEngine::GetRasDeviceParams",
      &v22,
      v7,
      &v29,
      v21,
      (unsigned int)a2);
  v22 = (*(&VPNIKEProtocolEngine::PEHelperFunctions + 1))(a2, 0, 0, 0, dwBytes);
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v34) = 0;
    LOWORD(v30) = 0;
    ConvertPortNoToString(&v30, (unsigned int)a2);
    FormatRRASErrorString(&v34, L"RasDeviceGetInfo=%d,s=%d", v22, dwBytes[0]);
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)&v34,
        (unsigned int)&v29,
        0,
        (__int64)&v30);
  }
  if ( v22 != 603 && v22 )
    goto LABEL_34;
  v9 = dwBytes[0];
  if ( !dwBytes[0] )
  {
    v9 = 64;
    dwBytes[0] = 64;
  }
  v10 = v9;
  ProcessHeap = GetProcessHeap();
  v12 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v10);
  v13 = v12;
  if ( v12 )
  {
    v14 = dwBytes[0] - 8;
    v22 = (*(&VPNIKEProtocolEngine::PEHelperFunctions + 1))(a2, 0, 0, v12, dwBytes);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v34) = 0;
      LOWORD(v30) = 0;
      ConvertPortNoToString(&v30, (unsigned int)a2);
      LODWORD(v20) = *v13;
      FormatRRASErrorString(&v34, L"RasDeviceGetInfo=%d,s=%d,noParams=%d", v22, dwBytes[0], v20);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v34,
          (unsigned int)&v29,
          0,
          (__int64)&v30);
    }
    if ( !v22 )
    {
      v15 = 0;
      for ( i = (STRSAFE_PCNZCH *)(v13 + 2); v15 < *v13; v14 -= 56 )
      {
        if ( v14 < 0x38 )
          break;
        if ( !_stricmp((const char *)i, "PhoneNumber") )
        {
          if ( a4 )
            StringCchCopyNA(a4, 0x81u, i[6], *((unsigned int *)i + 10));
        }
        else if ( !_stricmp((const char *)i, "DevSpecificInfo") && *((_DWORD *)i + 11) == 40 )
        {
          *(_QWORD *)a3 = *(STRSAFE_PCNZCH *)((char *)i + *((unsigned int *)i + 10) + 8);
        }
        ++v15;
        i += 7;
      }
      if ( *(_QWORD *)a3 )
      {
        if ( !a4 || (v17 = *a4 == 0, v22 = 749, !v17) )
          v22 = 0;
      }
      else
      {
        v22 = 837;
      }
    }
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v13);
LABEL_34:
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v34) = 0;
      LOWORD(v30) = 0;
      ConvertPortNoToString(&v30, (unsigned int)a2);
      FormatRRASErrorString(&v34, L"ConnectionId=%I64X,Destination IP=%S", *(_QWORD *)a3, a4);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v34,
          (unsigned int)&v29,
          0,
          (__int64)&v30);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, v22);
    }
    v8 = v22;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&dwBytes[1]);
  return v8;
}

```

## disassembly

```asm
0x180003e80  mov     [rsp-8+arg_0], rbx
0x180003e85  push    rbp
0x180003e86  push    rsi
0x180003e87  push    rdi
0x180003e88  push    r12
0x180003e8a  push    r13
0x180003e8c  push    r14
0x180003e8e  push    r15
0x180003e90  lea     rbp, [rsp-7D0h]
0x180003e98  sub     rsp, 8D0h
0x180003e9f  mov     rax, cs:__security_cookie
0x180003ea6  xor     rax, rsp
0x180003ea9  mov     [rbp+800h+var_40], rax
0x180003eb0  mov     r15, r9
0x180003eb3  mov     r13, r8
0x180003eb6  mov     r12, rdx
0x180003eb9  lea     rsi, WPP_GLOBAL_Control
0x180003ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ec7  cmp     rcx, rsi
0x180003eca  jz      short loc_180003EED
0x180003ecc  test    byte ptr [rcx+1Ch], 1
0x180003ed0  jz      short loc_180003EED
0x180003ed2  cmp     byte ptr [rcx+19h], 6
0x180003ed6  jb      short loc_180003EED
0x180003ed8  mov     edx, 2Fh ; '/'
0x180003edd  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180003ee4  mov     rcx, [rcx+10h]
0x180003ee8  call    WPP_SF_
0x180003eed  xor     ebx, ebx
0x180003eef  mov     [rsp+900h+var_8C0], ebx
0x180003ef3  mov     dword ptr [rsp+900h+dwBytes], ebx
0x180003ef7  mov     [rbp+800h+var_840], ebx
0x180003efa  xor     edx, edx; Val
0x180003efc  mov     r8d, 7FCh; Size
0x180003f02  lea     rcx, [rbp+800h+var_83C]; void *
0x180003f06  call    memset_0
0x180003f0b  mov     [rbp+800h+var_870], ebx
0x180003f0e  xorps   xmm0, xmm0
0x180003f11  xor     eax, eax
0x180003f13  movups  [rbp+800h+var_86C], xmm0
0x180003f17  movups  [rbp+800h+var_85C], xmm0
0x180003f1b  mov     [rbp+800h+var_84C], eax
0x180003f1e  movups  xmmword ptr [rbp+800h+var_880.Data1], xmm0
0x180003f22  xorps   xmm1, xmm1
0x180003f25  movdqu  [rsp+900h+var_8B0], xmm1
0x180003f2b  mov     qword ptr [rsp+900h+dwBytes+4], rbx
0x180003f30  movdqu  [rsp+900h+var_8A0], xmm0
0x180003f36  mov     [rsp+900h+var_890], rbx
0x180003f3b  mov     [rsp+900h+var_888], 0FFFFFFFFh
0x180003f43  mov     [rsp+900h+var_884], ebx
0x180003f47  lea     edi, [rbx+8]
0x180003f4a  test    cs:byte_1800AA941, dil
0x180003f51  jz      short loc_180003F77
0x180003f53  mov     [rsp+900h+var_8D0], r12d; unsigned int
0x180003f58  lea     rax, [rbp+800h+var_880]
0x180003f5c  mov     [rsp+900h+var_8E0], rax; struct _GUID *
0x180003f61  lea     r8, [rsp+900h+var_8C0]; unsigned int *
0x180003f66  lea     rdx, aVpnikeprotocol_0; "VPNIKEProtocolEngine::GetRasDeviceParam"...
0x180003f6d  lea     rcx, [rsp+900h+dwBytes+4]; this
0x180003f72  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180003f77  lea     rax, [rsp+900h+dwBytes]
0x180003f7c  mov     [rsp+900h+var_8E0], rax
0x180003f81  xor     r9d, r9d
0x180003f84  xor     r8d, r8d
0x180003f87  xor     edx, edx
0x180003f89  mov     rcx, r12
0x180003f8c  mov     rax, qword ptr cs:?PEHelperFunctions@VPNIKEProtocolEngine@@2U_PROTOCOL_ENGINE_HELPER_FUNCTIONS@@A+8; _PROTOCOL_ENGINE_HELPER_FUNCTIONS VPNIKEProtocolEngine::PEHelperFunctions
0x180003f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f98  mov     [rsp+900h+var_8C0], eax
0x180003f9c  test    cs:byte_1800AA941, 4
0x180003fa3  jz      short loc_180004005
0x180003fa5  mov     word ptr [rbp+800h+var_840], bx
0x180003fa9  mov     word ptr [rbp+800h+var_870], bx
0x180003fad  mov     edx, r12d
0x180003fb0  lea     rcx, [rbp+800h+var_870]
0x180003fb4  call    ConvertPortNoToString
0x180003fb9  mov     r9d, dword ptr [rsp+900h+dwBytes]
0x180003fbe  mov     r8d, [rsp+900h+var_8C0]
0x180003fc3  lea     rdx, aRasdevicegetin_0; "RasDeviceGetInfo=%d,s=%d"
0x180003fca  lea     rcx, [rbp+800h+var_840]
0x180003fce  call    FormatRRASErrorString
0x180003fd3  test    cs:byte_1800AA941, 4
0x180003fda  jz      short loc_180004005
0x180003fdc  lea     rax, [rbp+800h+var_870]
0x180003fe0  mov     [rsp+900h+var_8D8], rax
0x180003fe5  mov     [rsp+900h+var_8E0], rbx
0x180003fea  lea     r9, [rbp+800h+var_880]
0x180003fee  lea     r8, [rbp+800h+var_840]
0x180003ff2  lea     rdx, RasVpnIkeParamTraceError
0x180003ff9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004000  call    McTemplateU0zjzz_EventWriteTransfer
0x180004005  mov     eax, [rsp+900h+var_8C0]
0x180004009  cmp     eax, 25Bh
0x18000400e  jz      short loc_180004018
0x180004010  test    eax, eax
0x180004012  jnz     loc_1800041AB
0x180004018  mov     eax, dword ptr [rsp+900h+dwBytes]
0x18000401c  test    eax, eax
0x18000401e  jnz     short loc_180004029
0x180004020  mov     eax, 40h ; '@'
0x180004025  mov     dword ptr [rsp+900h+dwBytes], eax
0x180004029  mov     ebx, eax
0x18000402b  call    cs:__imp_GetProcessHeap
0x180004031  mov     r8d, ebx; dwBytes
0x180004034  mov     edx, edi; dwFlags
0x180004036  mov     rcx, rax; hHeap
0x180004039  call    cs:__imp_HeapAlloc
0x18000403f  mov     rsi, rax
0x180004042  xor     ebx, ebx
0x180004044  test    rax, rax
0x180004047  jz      loc_180004247
0x18000404d  mov     r14d, dword ptr [rsp+900h+dwBytes]
0x180004052  add     r14d, 0FFFFFFF8h
0x180004056  lea     rax, [rsp+900h+dwBytes]
0x18000405b  mov     [rsp+900h+var_8E0], rax
0x180004060  mov     r9, rsi
0x180004063  xor     r8d, r8d
0x180004066  xor     edx, edx
0x180004068  mov     rcx, r12
0x18000406b  mov     rax, qword ptr cs:?PEHelperFunctions@VPNIKEProtocolEngine@@2U_PROTOCOL_ENGINE_HELPER_FUNCTIONS@@A+8; _PROTOCOL_ENGINE_HELPER_FUNCTIONS VPNIKEProtocolEngine::PEHelperFunctions
0x180004072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004077  mov     [rsp+900h+var_8C0], eax
0x18000407b  test    cs:byte_1800AA941, 4
0x180004082  jz      short loc_1800040EA
0x180004084  mov     word ptr [rbp+800h+var_840], bx
0x180004088  mov     word ptr [rbp+800h+var_870], bx
0x18000408c  mov     edx, r12d
0x18000408f  lea     rcx, [rbp+800h+var_870]
0x180004093  call    ConvertPortNoToString
0x180004098  mov     eax, [rsi]
0x18000409a  mov     dword ptr [rsp+900h+var_8E0], eax
0x18000409e  mov     r9d, dword ptr [rsp+900h+dwBytes]
0x1800040a3  mov     r8d, [rsp+900h+var_8C0]
0x1800040a8  lea     rdx, aRasdevicegetin; "RasDeviceGetInfo=%d,s=%d,noParams=%d"
0x1800040af  lea     rcx, [rbp+800h+var_840]
0x1800040b3  call    FormatRRASErrorString
0x1800040b8  test    cs:byte_1800AA941, 4
0x1800040bf  jz      short loc_1800040EA
0x1800040c1  lea     rax, [rbp+800h+var_870]
0x1800040c5  mov     [rsp+900h+var_8D8], rax
0x1800040ca  mov     [rsp+900h+var_8E0], rbx
0x1800040cf  lea     r9, [rbp+800h+var_880]
0x1800040d3  lea     r8, [rbp+800h+var_840]
0x1800040d7  lea     rdx, RasVpnIkeParamTraceError
0x1800040de  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800040e5  call    McTemplateU0zjzz_EventWriteTransfer
0x1800040ea  cmp     [rsp+900h+var_8C0], ebx
0x1800040ee  jnz     loc_180004190
0x1800040f4  mov     edi, ebx
0x1800040f6  lea     rbx, [rsi+8]
0x1800040fa  cmp     [rsi], edi
0x1800040fc  jbe     short loc_180004168
0x1800040fe  cmp     r14d, 38h ; '8'
0x180004102  jb      short loc_180004168
0x180004104  lea     rdx, String2; "PhoneNumber"
0x18000410b  mov     rcx, rbx; String1
0x18000410e  call    cs:__imp__stricmp
0x180004114  test    eax, eax
0x180004116  jnz     short loc_180004134
0x180004118  test    r15, r15
0x18000411b  jz      short loc_18000415A
0x18000411d  mov     r9d, [rbx+28h]; cchToCopy
0x180004121  mov     r8, [rbx+30h]; pszSrc
0x180004125  mov     edx, 81h; cchDest
0x18000412a  mov     rcx, r15; pszDest
0x18000412d  call    StringCchCopyNA
0x180004132  jmp     short loc_18000415A
0x180004134  lea     rdx, aDevspecificinf; "DevSpecificInfo"
0x18000413b  mov     rcx, rbx; String1
0x18000413e  call    cs:__imp__stricmp
0x180004144  test    eax, eax
0x180004146  jnz     short loc_18000415A
0x180004148  cmp     dword ptr [rbx+2Ch], 28h ; '('
0x18000414c  jnz     short loc_18000415A
0x18000414e  mov     eax, [rbx+28h]
0x180004151  mov     rcx, [rax+rbx+8]
0x180004156  mov     [r13+0], rcx
0x18000415a  inc     edi
0x18000415c  add     rbx, 38h ; '8'
0x180004160  add     r14d, 0FFFFFFC8h
0x180004164  cmp     edi, [rsi]
0x180004166  jb      short loc_1800040FE
0x180004168  xor     ebx, ebx
0x18000416a  cmp     [r13+0], rbx
0x18000416e  jnz     short loc_18000417A
0x180004170  mov     [rsp+900h+var_8C0], 345h
0x180004178  jmp     short loc_180004190
0x18000417a  test    r15, r15
0x18000417d  jz      short loc_18000418C
0x18000417f  cmp     [r15], bl
0x180004182  mov     [rsp+900h+var_8C0], 2EDh
0x18000418a  jz      short loc_180004190
0x18000418c  mov     [rsp+900h+var_8C0], ebx
0x180004190  call    cs:__imp_GetProcessHeap
0x180004196  mov     rcx, rax; hHeap
0x180004199  mov     r8, rsi; lpMem
0x18000419c  xor     edx, edx; dwFlags
0x18000419e  call    cs:__imp_HeapFree
0x1800041a4  lea     rsi, WPP_GLOBAL_Control
0x1800041ab  test    cs:byte_1800AA941, 4
0x1800041b2  jz      short loc_180004211
0x1800041b4  mov     word ptr [rbp+800h+var_840], bx
0x1800041b8  mov     word ptr [rbp+800h+var_870], bx
0x1800041bc  mov     edx, r12d
0x1800041bf  lea     rcx, [rbp+800h+var_870]
0x1800041c3  call    ConvertPortNoToString
0x1800041c8  mov     r9, r15
0x1800041cb  mov     r8, [r13+0]
0x1800041cf  lea     rdx, aConnectionidI6; "ConnectionId=%I64X,Destination IP=%S"
0x1800041d6  lea     rcx, [rbp+800h+var_840]
0x1800041da  call    FormatRRASErrorString
0x1800041df  test    cs:byte_1800AA941, 4
0x1800041e6  jz      short loc_180004211
0x1800041e8  lea     rax, [rbp+800h+var_870]
0x1800041ec  mov     [rsp+900h+var_8D8], rax
0x1800041f1  mov     [rsp+900h+var_8E0], rbx
0x1800041f6  lea     r9, [rbp+800h+var_880]
0x1800041fa  lea     r8, [rbp+800h+var_840]
0x1800041fe  lea     rdx, RasVpnIkeParamTraceError
0x180004205  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000420c  call    McTemplateU0zjzz_EventWriteTransfer
0x180004211  mov     rcx, cs:WPP_GLOBAL_Control
0x180004218  cmp     rcx, rsi
0x18000421b  jz      short loc_180004243
0x18000421d  test    byte ptr [rcx+1Ch], 1
0x180004221  jz      short loc_180004243
0x180004223  cmp     byte ptr [rcx+19h], 6
0x180004227  jb      short loc_180004243
0x180004229  mov     edx, 30h ; '0'
0x18000422e  mov     r9d, [rsp+900h+var_8C0]
0x180004233  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x18000423a  mov     rcx, [rcx+10h]
0x18000423e  call    WPP_SF_d
0x180004243  mov     edi, [rsp+900h+var_8C0]
0x180004247  lea     rcx, [rsp+900h+dwBytes+4]; this
0x18000424c  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180004251  mov     eax, edi
0x180004253  mov     rcx, [rbp+800h+var_40]
0x18000425a  xor     rcx, rsp; StackCookie
0x18000425d  call    __security_check_cookie
0x180004262  mov     rbx, [rsp+900h+arg_0]
0x18000426a  add     rsp, 8D0h
0x180004271  pop     r15
0x180004273  pop     r14
0x180004275  pop     r13
0x180004277  pop     r12
0x180004279  pop     rdi
0x18000427a  pop     rsi
0x18000427b  pop     rbp
0x18000427c  retn
```
