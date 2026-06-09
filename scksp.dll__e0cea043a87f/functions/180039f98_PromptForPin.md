# PromptForPin

- ea: `0x180039f98`
- end: `0x18003a124`
- name: `PromptForPin`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a1a4`

## callees

- `0x180009e82`
- `0x18000d9d0`
- `0x180039994`
- `0x180039a44`
- `0x180039bf0`
- `0x180039f98`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003a10e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003a10e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a100`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a0f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a0f2`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x18003a093`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x18003a093`

## pseudocode

```c
__int64 __fastcall PromptForPin(__int64 a1)
{
  void *v2; // r14
  struct _TP_TIMER *v3; // rsi
  const WCHAR *v4; // rax
  DWORD v5; // edi
  unsigned int v6; // ecx
  _BYTE *v7; // rcx
  __int64 v8; // rax
  LPVOID pv; // [rsp+50h] [rbp-79h] BYREF
  void *v11; // [rsp+58h] [rbp-71h] BYREF
  struct _TP_TIMER *v12; // [rsp+60h] [rbp-69h] BYREF
  struct _CREDUI_INFOW pUiInfo; // [rsp+70h] [rbp-59h] BYREF
  _QWORD v14[11]; // [rsp+C8h] [rbp-1h] BYREF
  ULONG pulOutAuthBufferSize; // [rsp+130h] [rbp+67h] BYREF
  ULONG ulInAuthBufferSize; // [rsp+138h] [rbp+6Fh] BYREF
  ULONG pulAuthPackage; // [rsp+140h] [rbp+77h] BYREF
  LPCVOID pvInAuthBuffer; // [rsp+148h] [rbp+7Fh] BYREF

  pvInAuthBuffer = 0;
  ulInAuthBufferSize = 0;
  v2 = 0;
  pv = 0;
  v3 = 0;
  pulOutAuthBufferSize = 0;
  pulAuthPackage = -5324;
  v11 = 0;
  v12 = 0;
  memset_0(&pUiInfo, 0, 0x88u);
  pUiInfo.hwndParent = *(HWND *)(a1 + 16);
  pUiInfo.pszMessageText = *(PCWSTR *)(a1 + 56);
  v4 = *(const WCHAR **)(a1 + 48);
  pUiInfo.cbSize = 136;
  if ( v4 )
    pUiInfo.pszCaptionText = v4;
  else
    pUiInfo.pszCaptionText = **(PCWSTR **)a1;
  v5 = I_FormatAndAllocateKerbCertificateLogon(a1, &pvInAuthBuffer, &ulInAuthBufferSize);
  if ( !v5 )
  {
    v6 = *(_DWORD *)(a1 + 124);
    if ( v6 )
    {
      GetAbortEvent(v6, &v11, &v12, v14);
      v2 = v11;
      v3 = v12;
    }
    v5 = CredUIPromptForWindowsCredentialsW(
           &pUiInfo,
           0,
           &pulAuthPackage,
           pvInAuthBuffer,
           ulInAuthBufferSize,
           &pv,
           &pulOutAuthBufferSize,
           0,
           *(_DWORD *)(a1 + 120) | 0x20);
    if ( !v5 )
    {
      if ( pulAuthPackage == -5324 )
        v5 = I_UnpackPin(a1, pv, pulOutAuthBufferSize);
      else
        v5 = 1359;
    }
  }
  if ( pvInAuthBuffer )
    CspFreeH(pvInAuthBuffer);
  v7 = pv;
  if ( pv )
  {
    v8 = pulOutAuthBufferSize;
    if ( pulOutAuthBufferSize )
    {
      do
      {
        *v7++ = 0;
        --v8;
      }
      while ( v8 );
      v7 = pv;
    }
    CoTaskMemFree(v7);
  }
  if ( v2 )
    CloseHandle(v2);
  if ( v3 )
    CloseThreadpoolTimer(v3);
  return v5;
}

```

## disassembly

```asm
0x180039f98  push    rbp
0x180039f9a  push    rbx
0x180039f9b  push    rsi
0x180039f9c  push    rdi
0x180039f9d  push    r14
0x180039f9f  lea     rbp, [rsp-37h]
0x180039fa4  sub     rsp, 100h
0x180039fab  mov     rbx, rcx
0x180039fae  mov     [rbp+57h+pvInAuthBuffer], 0
0x180039fb6  mov     edi, 88h
0x180039fbb  mov     [rbp+57h+arg_8], 0
0x180039fc2  xor     r14d, r14d
0x180039fc5  mov     [rbp+57h+pv], 0
0x180039fcd  xor     esi, esi
0x180039fcf  mov     [rbp+57h+arg_0], 0
0x180039fd6  mov     r8d, edi; Size
0x180039fd9  mov     [rbp+57h+pulAuthPackage], 0FFFFEB34h
0x180039fe0  xor     edx, edx; Val
0x180039fe2  mov     [rbp+57h+var_C8], r14
0x180039fe6  lea     rcx, [rbp+57h+pUiInfo]; void *
0x180039fea  mov     [rbp+57h+var_C0], rsi
0x180039fee  call    memset_0
0x180039ff3  mov     rax, [rbx+10h]
0x180039ff7  mov     [rbp+57h+pUiInfo.hwndParent], rax
0x180039ffb  mov     rax, [rbx+38h]
0x180039fff  mov     [rbp+57h+pUiInfo.pszMessageText], rax
0x18003a003  mov     rax, [rbx+30h]
0x18003a007  mov     [rbp+57h+pUiInfo.cbSize], edi
0x18003a00a  test    rax, rax
0x18003a00d  jz      short loc_18003A015
0x18003a00f  mov     [rbp+57h+pUiInfo.pszCaptionText], rax
0x18003a013  jmp     short loc_18003A01F
0x18003a015  mov     rax, [rbx]
0x18003a018  mov     rcx, [rax]
0x18003a01b  mov     [rbp+57h+pUiInfo.pszCaptionText], rcx
0x18003a01f  lea     r8, [rbp+57h+arg_8]
0x18003a023  mov     rcx, rbx
0x18003a026  lea     rdx, [rbp+57h+pvInAuthBuffer]
0x18003a02a  call    I_FormatAndAllocateKerbCertificateLogon
0x18003a02f  mov     edi, eax
0x18003a031  test    eax, eax
0x18003a033  jnz     loc_18003A0C1
0x18003a039  mov     ecx, [rbx+7Ch]
0x18003a03c  test    ecx, ecx
0x18003a03e  jz      short loc_18003A059
0x18003a040  lea     r9, [rbp+57h+var_58]
0x18003a044  lea     r8, [rbp+57h+var_C0]
0x18003a048  lea     rdx, [rbp+57h+var_C8]
0x18003a04c  call    GetAbortEvent
0x18003a051  mov     r14, [rbp+57h+var_C8]
0x18003a055  mov     rsi, [rbp+57h+var_C0]
0x18003a059  mov     eax, [rbx+78h]
0x18003a05c  lea     r8, [rbp+57h+pulAuthPackage]; pulAuthPackage
0x18003a060  mov     r9, [rbp+57h+pvInAuthBuffer]; pvInAuthBuffer
0x18003a064  lea     rcx, [rbp+57h+pUiInfo]; pUiInfo
0x18003a068  or      eax, 20h
0x18003a06b  xor     edx, edx; dwAuthError
0x18003a06d  mov     [rsp+120h+dwFlags], eax; dwFlags
0x18003a071  lea     rax, [rbp+57h+arg_0]
0x18003a075  mov     [rsp+120h+pfSave], 0; pfSave
0x18003a07e  mov     [rsp+120h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x18003a083  lea     rax, [rbp+57h+pv]
0x18003a087  mov     [rsp+120h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x18003a08c  mov     eax, [rbp+57h+arg_8]
0x18003a08f  mov     [rsp+120h+ulInAuthBufferSize], eax; ulInAuthBufferSize
0x18003a093  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x18003a099  mov     edi, eax
0x18003a09b  test    eax, eax
0x18003a09d  jnz     short loc_18003A0C1
0x18003a09f  cmp     [rbp+57h+pulAuthPackage], 0FFFFEB34h
0x18003a0a6  jz      short loc_18003A0AF
0x18003a0a8  mov     edi, 54Fh
0x18003a0ad  jmp     short loc_18003A0C1
0x18003a0af  mov     r8d, [rbp+57h+arg_0]
0x18003a0b3  mov     rcx, rbx
0x18003a0b6  mov     rdx, [rbp+57h+pv]
0x18003a0ba  call    I_UnpackPin
0x18003a0bf  mov     edi, eax
0x18003a0c1  cmp     [rbp+57h+pvInAuthBuffer], 0
0x18003a0c6  jz      short loc_18003A0D1
0x18003a0c8  mov     rcx, [rbp+57h+pvInAuthBuffer]
0x18003a0cc  call    CspFreeH
0x18003a0d1  mov     rcx, [rbp+57h+pv]
0x18003a0d5  test    rcx, rcx
0x18003a0d8  jz      short loc_18003A0F8
0x18003a0da  mov     eax, [rbp+57h+arg_0]
0x18003a0dd  test    rax, rax
0x18003a0e0  jz      short loc_18003A0F2
0x18003a0e2  mov     byte ptr [rcx], 0
0x18003a0e5  inc     rcx
0x18003a0e8  sub     rax, 1
0x18003a0ec  jnz     short loc_18003A0E2
0x18003a0ee  mov     rcx, [rbp+57h+pv]; pv
0x18003a0f2  call    cs:__imp_CoTaskMemFree
0x18003a0f8  test    r14, r14
0x18003a0fb  jz      short loc_18003A106
0x18003a0fd  mov     rcx, r14; hObject
0x18003a100  call    cs:__imp_CloseHandle
0x18003a106  test    rsi, rsi
0x18003a109  jz      short loc_18003A114
0x18003a10b  mov     rcx, rsi; pti
0x18003a10e  call    cs:__imp_CloseThreadpoolTimer
0x18003a114  mov     eax, edi
0x18003a116  add     rsp, 100h
0x18003a11d  pop     r14
0x18003a11f  pop     rdi
0x18003a120  pop     rsi
0x18003a121  pop     rbx
0x18003a122  pop     rbp
0x18003a123  retn
```
