# CBlbBackupAsync::PublishAppConsistencyEvents(void)

- ea: `0x14003299c`
- end: `0x140032d49`
- name: `?PublishAppConsistencyEvents@CBlbBackupAsync@@AEAAJXZ`
- size: `941`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14003299c`
- `0x1400d3400`
- `0x1400e9cc8`
- `0x1400ea028`
- `0x1400ea5c8`

## import_xrefs

- `KERNEL32!FileTimeToLocalFileTime` at `0x140032a48`
- `KERNEL32!FileTimeToLocalFileTime` at `0x140032a48`
- `KERNEL32!GetLastError` at `0x140032a52`
- `KERNEL32!GetLastError` at `0x140032a52`
- `ole32!CoTaskMemFree` at `0x140032bb1`
- `ole32!CoTaskMemFree` at `0x140032bc5`
- `ole32!CoTaskMemFree` at `0x140032bde`
- `ole32!CoTaskMemFree` at `0x140032bf2`
- `ole32!CoTaskMemFree` at `0x140032cc1`
- `ole32!CoTaskMemFree` at `0x140032cd6`
- `ole32!CoTaskMemFree` at `0x140032ceb`
- `ole32!CoTaskMemFree` at `0x140032d00`
- `ole32!CoTaskMemFree` at `0x140032bb1`
- `ole32!CoTaskMemFree` at `0x140032bc5`
- `ole32!CoTaskMemFree` at `0x140032bde`
- `ole32!CoTaskMemFree` at `0x140032bf2`
- `ole32!CoTaskMemFree` at `0x140032cc1`
- `ole32!CoTaskMemFree` at `0x140032cd6`
- `ole32!CoTaskMemFree` at `0x140032ceb`
- `ole32!CoTaskMemFree` at `0x140032d00`

## string_xrefs

- `0x140032a02`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400329f6`: `m_pComponentBackupHelper`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::PublishAppConsistencyEvents(CBlbBackupAsync *this)
{
  void *v2; // rsi
  unsigned __int16 *v3; // r14
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // r15
  signed int LastError; // eax
  signed int ComponentInfo; // ebx
  PVOID *v8; // rcx
  unsigned int NumComponents; // eax
  unsigned int i; // r12d
  const struct CBlbComponentBackupContext *Component; // rax
  unsigned __int16 *v13; // [rsp+70h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int16 *v15; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int16 *v16; // [rsp+88h] [rbp-31h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v18[8]; // [rsp+98h] [rbp-21h] BYREF
  struct _GUID v19; // [rsp+A0h] [rbp-19h] BYREF
  struct _GUID v20; // [rsp+B0h] [rbp-9h] BYREF
  struct _GUID v21; // [rsp+C0h] [rbp+7h] BYREF
  unsigned __int8 v22; // [rsp+120h] [rbp+67h] BYREF
  unsigned __int8 v23; // [rsp+128h] [rbp+6Fh] BYREF
  int v24; // [rsp+130h] [rbp+77h]
  unsigned int v25; // [rsp+138h] [rbp+7Fh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 618, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( !*((_QWORD *)this + 101) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x3886u, "m_pComponentBackupHelper");
  v2 = 0;
  v3 = 0;
  pv = 0;
  v4 = 0;
  v15 = 0;
  v5 = 0;
  v13 = 0;
  v16 = 0;
  v19 = GUID_NULL;
  LocalFileTime = 0;
  v21 = GUID_NULL;
  if ( !FileTimeToLocalFileTime((const FILETIME *)this + 49, &LocalFileTime) )
  {
    LastError = GetLastError();
    ComponentInfo = LastError;
    if ( LastError > 0 )
      ComponentInfo = (unsigned __int16)LastError | 0x80070000;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 619, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        goto LABEL_49;
      }
      goto LABEL_50;
    }
    return (unsigned int)ComponentInfo;
  }
  ComponentInfo = 0;
  NumComponents = CBlbComponentBackupHelper::GetNumComponents(*((CBlbComponentBackupHelper **)this + 101));
  v25 = NumComponents;
  for ( i = 0; ; ++i )
  {
    if ( i >= NumComponents )
      goto LABEL_40;
    Component = CBlbComponentBackupHelper::GetComponent(*((CBlbComponentBackupHelper **)this + 101), i);
    if ( *((_BYTE *)Component + 90) == 1 )
    {
      v24 = *((_DWORD *)Component + 25);
      if ( v24 < 0 && *((_DWORD *)Component + 23) == 1 )
        break;
    }
LABEL_29:
    NumComponents = v25;
  }
  ComponentInfo = CBlbComponentBackupContext::GetComponentInfo(
                    Component,
                    (unsigned __int16 **)&pv,
                    &v15,
                    &v13,
                    &v16,
                    &v19,
                    &v21,
                    &v20,
                    &v23,
                    &v22,
                    (enum EReasonForExclusion *)v18,
                    0,
                    0);
  if ( ComponentInfo < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v2 = pv;
      v3 = v15;
      v4 = v13;
      v5 = v16;
      goto LABEL_41;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 620, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    v2 = pv;
    v3 = v15;
    v4 = v13;
    v5 = v16;
LABEL_40:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  v5 = v16;
  v3 = v15;
  v2 = pv;
  v20 = v19;
  ComponentInfo = PublishAdminAppConsistencyCheckFailureEvent(
                    (unsigned __int16 *)pv,
                    v15,
                    v16,
                    &v20,
                    v24,
                    LocalFileTime);
  if ( ComponentInfo >= 0 )
  {
    if ( v2 )
    {
      CoTaskMemFree(v2);
      v2 = 0;
      pv = 0;
    }
    if ( v3 )
    {
      CoTaskMemFree(v3);
      v3 = 0;
      v15 = 0;
    }
    v4 = v13;
    if ( v13 )
    {
      CoTaskMemFree(v13);
      v4 = 0;
      v13 = 0;
    }
    if ( v5 )
    {
      CoTaskMemFree(v5);
      v5 = 0;
      v16 = 0;
    }
    goto LABEL_29;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 621, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = v13;
  ComponentInfo = 0;
LABEL_41:
  if ( v2 )
  {
    CoTaskMemFree(v2);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    CoTaskMemFree(v3);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    CoTaskMemFree(v4);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    CoTaskMemFree(v5);
LABEL_49:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_50:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_(v8[2], 622, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  return (unsigned int)ComponentInfo;
}

```

## disassembly

```asm
0x14003299c  push    rbp
0x14003299e  push    rbx
0x14003299f  push    rsi
0x1400329a0  push    rdi
0x1400329a1  push    r12
0x1400329a3  push    r13
0x1400329a5  push    r14
0x1400329a7  push    r15
0x1400329a9  lea     rbp, [rsp-1Fh]
0x1400329ae  sub     rsp, 0D8h
0x1400329b5  mov     r13, rcx
0x1400329b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400329bf  lea     rax, WPP_GLOBAL_Control
0x1400329c6  cmp     rcx, rax
0x1400329c9  jz      short loc_1400329EC
0x1400329cb  test    byte ptr [rcx+1Ch], 1
0x1400329cf  jz      short loc_1400329EC
0x1400329d1  cmp     byte ptr [rcx+19h], 4
0x1400329d5  jb      short loc_1400329EC
0x1400329d7  mov     rcx, [rcx+10h]
0x1400329db  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400329e2  mov     edx, 26Ah
0x1400329e7  call    WPP_SF_
0x1400329ec  cmp     qword ptr [r13+328h], 0
0x1400329f4  jnz     short loc_140032A0E
0x1400329f6  lea     r8, aMPcomponentbac; "m_pComponentBackupHelper"
0x1400329fd  mov     edx, 3886h; unsigned int
0x140032a02  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140032a09  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140032a0e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140032a15  xor     esi, esi
0x140032a17  lea     rcx, [r13+188h]; lpFileTime
0x140032a1e  xor     r14d, r14d
0x140032a21  mov     [rbp+57h+pv], rsi
0x140032a25  xor     edi, edi
0x140032a27  mov     [rbp+57h+var_90], r14
0x140032a2b  xor     r15d, r15d
0x140032a2e  mov     [rbp+57h+var_A0], rdi
0x140032a32  lea     rdx, [rbp+57h+LocalFileTime]; lpLocalFileTime
0x140032a36  mov     [rbp+57h+var_88], r15
0x140032a3a  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x140032a3f  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], rsi
0x140032a43  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x140032a48  call    cs:__imp_FileTimeToLocalFileTime
0x140032a4e  test    eax, eax
0x140032a50  jnz     short loc_140032AAF
0x140032a52  call    cs:__imp_GetLastError
0x140032a58  mov     ebx, eax
0x140032a5a  test    eax, eax
0x140032a5c  jle     short loc_140032A67
0x140032a5e  movzx   ebx, ax
0x140032a61  or      ebx, 80070000h
0x140032a67  mov     rcx, cs:WPP_GLOBAL_Control
0x140032a6e  lea     r12, WPP_GLOBAL_Control
0x140032a75  cmp     rcx, r12
0x140032a78  jz      loc_140032D33
0x140032a7e  test    byte ptr [rcx+1Ch], 1
0x140032a82  jz      loc_140032D0D
0x140032a88  cmp     byte ptr [rcx+19h], 2
0x140032a8c  jb      loc_140032D0D
0x140032a92  mov     rcx, [rcx+10h]
0x140032a96  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140032a9d  mov     edx, 26Bh
0x140032aa2  mov     r9d, ebx
0x140032aa5  call    WPP_SF_d
0x140032aaa  jmp     loc_140032D06
0x140032aaf  mov     rcx, [r13+328h]; this
0x140032ab6  xor     ebx, ebx
0x140032ab8  call    ?GetNumComponents@CBlbComponentBackupHelper@@QEBAKXZ; CBlbComponentBackupHelper::GetNumComponents(void)
0x140032abd  mov     [rbp+57h+arg_18], eax
0x140032ac0  xor     r12d, r12d
0x140032ac3  cmp     r12d, eax
0x140032ac6  jnb     loc_140032CAB
0x140032acc  mov     rcx, [r13+328h]; this
0x140032ad3  mov     edx, r12d; unsigned int
0x140032ad6  call    ?GetComponent@CBlbComponentBackupHelper@@QEBAPEBVCBlbComponentBackupContext@@K@Z; CBlbComponentBackupHelper::GetComponent(ulong)
0x140032adb  cmp     byte ptr [rax+5Ah], 1
0x140032adf  jnz     loc_140032BFF
0x140032ae5  mov     ecx, [rax+64h]
0x140032ae8  mov     [rbp+57h+arg_10], ecx
0x140032aeb  test    ecx, ecx
0x140032aed  jns     loc_140032BFF
0x140032af3  cmp     dword ptr [rax+5Ch], 1
0x140032af7  jnz     loc_140032BFF
0x140032afd  mov     [rsp+110h+var_B0], 0; unsigned int *
0x140032b06  lea     rcx, [rbp+57h+var_78]
0x140032b0a  mov     [rsp+110h+var_B8], 0; struct _GUID **
0x140032b13  lea     r9, [rbp+57h+var_A0]; unsigned __int16 **
0x140032b17  mov     [rsp+110h+var_C0], rcx; enum EReasonForExclusion *
0x140032b1c  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x140032b20  lea     rcx, [rbp+57h+arg_0]
0x140032b24  mov     [rsp+110h+var_C8], rcx; unsigned __int8 *
0x140032b29  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x140032b2d  lea     rcx, [rbp+57h+arg_8]
0x140032b31  mov     [rsp+110h+var_D0], rcx; unsigned __int8 *
0x140032b36  lea     rcx, [rbp+57h+var_60]
0x140032b3a  mov     [rsp+110h+var_D8], rcx; struct _GUID *
0x140032b3f  lea     rcx, [rbp+57h+var_50]
0x140032b43  mov     [rsp+110h+var_E0], rcx; struct _GUID *
0x140032b48  lea     rcx, [rbp+57h+var_70]
0x140032b4c  mov     qword ptr [rsp+110h+var_E8.dwLowDateTime], rcx; struct _GUID *
0x140032b51  lea     rcx, [rbp+57h+var_88]
0x140032b55  mov     [rsp+110h+var_F0], rcx; unsigned __int16 **
0x140032b5a  mov     rcx, rax; this
0x140032b5d  call    ?GetComponentInfo@CBlbComponentBackupContext@@QEBAJPEAPEAG000AEAU_GUID@@11AEAE2AEAW4EReasonForExclusion@@PEAPEAU2@PEAK@Z; CBlbComponentBackupContext::GetComponentInfo(ushort * *,ushort * *,ushort * *,ushort * *,_GUID &,_GUID &,_GUID &,uchar &,uchar &,EReasonForExclusion &,_GUID * *,ulong *)
0x140032b62  mov     ebx, eax
0x140032b64  test    eax, eax
0x140032b66  js      loc_140032C50
0x140032b6c  mov     rax, qword ptr [rbp+57h+LocalFileTime.dwLowDateTime]
0x140032b70  lea     r9, [rbp+57h+var_60]; struct _GUID *
0x140032b74  movaps  xmm0, xmmword ptr [rbp+57h+var_70.Data1]
0x140032b78  mov     r15, [rbp+57h+var_88]
0x140032b7c  mov     r14, [rbp+57h+var_90]
0x140032b80  mov     r8, r15; unsigned __int16 *
0x140032b83  mov     rsi, [rbp+57h+pv]
0x140032b87  mov     rdx, r14; unsigned __int16 *
0x140032b8a  mov     qword ptr [rsp+110h+var_E8.dwLowDateTime], rax; struct _FILETIME
0x140032b8f  mov     rcx, rsi; unsigned __int16 *
0x140032b92  mov     eax, [rbp+57h+arg_10]
0x140032b95  mov     dword ptr [rsp+110h+var_F0], eax; char
0x140032b99  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x140032b9e  call    ?PublishAdminAppConsistencyCheckFailureEvent@@YAJPEAG00U_GUID@@JU_FILETIME@@@Z; PublishAdminAppConsistencyCheckFailureEvent(ushort *,ushort *,ushort *,_GUID,long,_FILETIME)
0x140032ba3  mov     ebx, eax
0x140032ba5  test    eax, eax
0x140032ba7  js      short loc_140032C0A
0x140032ba9  test    rsi, rsi
0x140032bac  jz      short loc_140032BBD
0x140032bae  mov     rcx, rsi; pv
0x140032bb1  call    cs:__imp_CoTaskMemFree
0x140032bb7  xor     esi, esi
0x140032bb9  mov     [rbp+57h+pv], rsi
0x140032bbd  test    r14, r14
0x140032bc0  jz      short loc_140032BD2
0x140032bc2  mov     rcx, r14; pv
0x140032bc5  call    cs:__imp_CoTaskMemFree
0x140032bcb  xor     r14d, r14d
0x140032bce  mov     [rbp+57h+var_90], r14
0x140032bd2  mov     rdi, [rbp+57h+var_A0]
0x140032bd6  test    rdi, rdi
0x140032bd9  jz      short loc_140032BEA
0x140032bdb  mov     rcx, rdi; pv
0x140032bde  call    cs:__imp_CoTaskMemFree
0x140032be4  xor     edi, edi
0x140032be6  mov     [rbp+57h+var_A0], rdi
0x140032bea  test    r15, r15
0x140032bed  jz      short loc_140032BFF
0x140032bef  mov     rcx, r15; pv
0x140032bf2  call    cs:__imp_CoTaskMemFree
0x140032bf8  xor     r15d, r15d
0x140032bfb  mov     [rbp+57h+var_88], r15
0x140032bff  mov     eax, [rbp+57h+arg_18]
0x140032c02  inc     r12d
0x140032c05  jmp     loc_140032AC3
0x140032c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140032c11  lea     r12, WPP_GLOBAL_Control
0x140032c18  cmp     rcx, r12
0x140032c1b  jz      short loc_140032C48
0x140032c1d  test    byte ptr [rcx+1Ch], 1
0x140032c21  jz      short loc_140032C48
0x140032c23  cmp     byte ptr [rcx+19h], 3
0x140032c27  jb      short loc_140032C48
0x140032c29  mov     rcx, [rcx+10h]
0x140032c2d  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140032c34  mov     edx, 26Dh
0x140032c39  mov     r9d, eax
0x140032c3c  call    WPP_SF_d
0x140032c41  mov     rcx, cs:WPP_GLOBAL_Control
0x140032c48  mov     rdi, [rbp+57h+var_A0]
0x140032c4c  xor     ebx, ebx
0x140032c4e  jmp     short loc_140032CB9
0x140032c50  mov     rcx, cs:WPP_GLOBAL_Control
0x140032c57  lea     r12, WPP_GLOBAL_Control
0x140032c5e  cmp     rcx, r12
0x140032c61  jz      short loc_140032C99
0x140032c63  test    byte ptr [rcx+1Ch], 1
0x140032c67  jz      short loc_140032C99
0x140032c69  cmp     byte ptr [rcx+19h], 2
0x140032c6d  jb      short loc_140032C99
0x140032c6f  mov     rcx, [rcx+10h]
0x140032c73  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140032c7a  mov     edx, 26Ch
0x140032c7f  mov     r9d, eax
0x140032c82  call    WPP_SF_d
0x140032c87  mov     rsi, [rbp+57h+pv]
0x140032c8b  mov     r14, [rbp+57h+var_90]
0x140032c8f  mov     rdi, [rbp+57h+var_A0]
0x140032c93  mov     r15, [rbp+57h+var_88]
0x140032c97  jmp     short loc_140032CB2
0x140032c99  mov     rsi, [rbp+57h+pv]
0x140032c9d  mov     r14, [rbp+57h+var_90]
0x140032ca1  mov     rdi, [rbp+57h+var_A0]
0x140032ca5  mov     r15, [rbp+57h+var_88]
0x140032ca9  jmp     short loc_140032CB9
0x140032cab  lea     r12, WPP_GLOBAL_Control
0x140032cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140032cb9  test    rsi, rsi
0x140032cbc  jz      short loc_140032CCE
0x140032cbe  mov     rcx, rsi; pv
0x140032cc1  call    cs:__imp_CoTaskMemFree
0x140032cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140032cce  test    r14, r14
0x140032cd1  jz      short loc_140032CE3
0x140032cd3  mov     rcx, r14; pv
0x140032cd6  call    cs:__imp_CoTaskMemFree
0x140032cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ce3  test    rdi, rdi
0x140032ce6  jz      short loc_140032CF8
0x140032ce8  mov     rcx, rdi; pv
0x140032ceb  call    cs:__imp_CoTaskMemFree
0x140032cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x140032cf8  test    r15, r15
0x140032cfb  jz      short loc_140032D0D
0x140032cfd  mov     rcx, r15; pv
0x140032d00  call    cs:__imp_CoTaskMemFree
0x140032d06  mov     rcx, cs:WPP_GLOBAL_Control
0x140032d0d  cmp     rcx, r12
0x140032d10  jz      short loc_140032D33
0x140032d12  test    byte ptr [rcx+1Ch], 1
0x140032d16  jz      short loc_140032D33
0x140032d18  cmp     byte ptr [rcx+19h], 4
0x140032d1c  jb      short loc_140032D33
0x140032d1e  mov     rcx, [rcx+10h]
0x140032d22  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140032d29  mov     edx, 26Eh
0x140032d2e  call    WPP_SF_
0x140032d33  mov     eax, ebx
0x140032d35  add     rsp, 0D8h
0x140032d3c  pop     r15
0x140032d3e  pop     r14
0x140032d40  pop     r13
0x140032d42  pop     r12
0x140032d44  pop     rdi
0x140032d45  pop     rsi
0x140032d46  pop     rbx
0x140032d47  pop     rbp
0x140032d48  retn
```
