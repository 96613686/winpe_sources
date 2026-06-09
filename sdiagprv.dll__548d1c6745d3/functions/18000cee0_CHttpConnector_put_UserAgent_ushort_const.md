# CHttpConnector::put_UserAgent(ushort const *)

- ea: `0x18000cee0`
- end: `0x18000d02a`
- name: `?put_UserAgent@CHttpConnector@@QEAAJPEBG@Z`
- size: `330`
- prototype: `__int64 __fastcall(CHttpConnector *this, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009c70`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18000cad8`
- `0x18000cee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfa8`
- `WINHTTP!WinHttpSetOption` at `0x18000cf9e`
- `WINHTTP!WinHttpSetOption` at `0x18000cf9e`

## string_xrefs

- `0x18000cf17`: `CHttpConnector::put_UserAgent`
- `0x18000cfd3`: `CHttpConnector::put_UserAgent`
- `0x18000d011`: `CHttpConnector::put_UserAgent`
- `0x18000cf0a`: `UserAgent`

## pseudocode

```c
__int64 __fastcall CHttpConnector::put_UserAgent(CHttpConnector *this, __int64 a2)
{
  unsigned int v2; // ebx
  _WORD *v3; // rax
  void *v4; // r10
  void *v5; // r11
  signed int LastError; // eax
  __int64 v7; // r9
  DWORD dwBufferLength; // [rsp+48h] [rbp+10h] BYREF

  dwBufferLength = 0;
  if ( !a2 )
  {
    v2 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CHttpConnector::put_UserAgent",
        -2147024809,
        (__int64)"UserAgent");
    return v2;
  }
  if ( !*(_QWORD *)this )
  {
    v2 = -2147019873;
    goto LABEL_21;
  }
  v3 = (_WORD *)a2;
  a2 = 0x7FFFFFFF;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --a2;
  }
  while ( a2 );
  v2 = a2 == 0 ? 0x80070057 : 0;
  if ( a2 )
  {
    v2 = ULongLongToULong((2 * (0x7FFFFFFF - a2)) & -(__int64)(a2 != 0), &dwBufferLength);
    if ( (v2 & 0x80000000) == 0 )
    {
      if ( WinHttpSetOption(v5, 0x29u, v4, dwBufferLength) )
      {
        v2 = 0;
        goto LABEL_17;
      }
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (v2 & 0x80000000) == 0 )
      {
        v2 = -2147467259;
        goto LABEL_21;
      }
    }
  }
  if ( v2 == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return v2;
    v7 = 2147942487LL;
    goto LABEL_25;
  }
  if ( v2 )
  {
LABEL_21:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return v2;
    v7 = v2;
LABEL_25:
    McTemplateU0sq_EventWriteTransfer(this, a2, "CHttpConnector::put_UserAgent", v7);
    return v2;
  }
LABEL_17:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CHttpConnector::put_UserAgent");
  return v2;
}

```

## disassembly

```asm
0x18000cee0  mov     [rsp+arg_0], rbx
0x18000cee5  push    rsi
0x18000cee6  sub     rsp, 30h
0x18000ceea  xor     esi, esi
0x18000ceec  mov     r10, rdx
0x18000ceef  mov     [rsp+38h+dwBufferLength], esi
0x18000cef3  test    rdx, rdx
0x18000cef6  jnz     short loc_18000CF2D
0x18000cef8  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000ceff  mov     ebx, 80070057h
0x18000cf04  jz      loc_18000D01D
0x18000cf0a  lea     rax, aUseragent; "UserAgent"
0x18000cf11  mov     r9d, 80070057h
0x18000cf17  lea     r8, aChttpconnector_7; "CHttpConnector::put_UserAgent"
0x18000cf1e  mov     [rsp+38h+var_18], rax
0x18000cf23  call    McTemplateU0sqs_EventWriteTransfer
0x18000cf28  jmp     loc_18000D01D
0x18000cf2d  mov     r11, [rcx]
0x18000cf30  test    r11, r11
0x18000cf33  jnz     short loc_18000CF3F
0x18000cf35  mov     ebx, 8007139Fh
0x18000cf3a  jmp     loc_18000CFF4
0x18000cf3f  mov     r8d, 7FFFFFFFh
0x18000cf45  mov     rax, r10
0x18000cf48  mov     edx, r8d
0x18000cf4b  cmp     [rax], si
0x18000cf4e  jz      short loc_18000CF5A
0x18000cf50  add     rax, 2
0x18000cf54  sub     rdx, 1
0x18000cf58  jnz     short loc_18000CF4B
0x18000cf5a  mov     rax, rdx
0x18000cf5d  neg     rax
0x18000cf60  sbb     ebx, ebx
0x18000cf62  not     ebx
0x18000cf64  and     ebx, 80070057h
0x18000cf6a  test    rdx, rdx
0x18000cf6d  jz      short loc_18000CFE8
0x18000cf6f  sub     r8, rdx
0x18000cf72  add     r8, r8
0x18000cf75  neg     rdx
0x18000cf78  lea     rdx, [rsp+38h+dwBufferLength]; unsigned int *
0x18000cf7d  sbb     rcx, rcx
0x18000cf80  and     rcx, r8; unsigned __int64
0x18000cf83  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000cf88  mov     ebx, eax
0x18000cf8a  test    eax, eax
0x18000cf8c  js      short loc_18000CFE8
0x18000cf8e  mov     r9d, [rsp+38h+dwBufferLength]; dwBufferLength
0x18000cf93  mov     r8, r10; lpBuffer
0x18000cf96  mov     edx, 29h ; ')'; dwOption
0x18000cf9b  mov     rcx, r11; hInternet
0x18000cf9e  call    cs:__imp_WinHttpSetOption
0x18000cfa4  test    eax, eax
0x18000cfa6  jnz     short loc_18000CFC8
0x18000cfa8  call    cs:__imp_GetLastError
0x18000cfae  mov     ebx, eax
0x18000cfb0  test    eax, eax
0x18000cfb2  jle     short loc_18000CFBD
0x18000cfb4  movzx   ebx, ax
0x18000cfb7  or      ebx, 80070000h
0x18000cfbd  test    ebx, ebx
0x18000cfbf  js      short loc_18000CFE8
0x18000cfc1  mov     ebx, 80004005h
0x18000cfc6  jmp     short loc_18000CFF4
0x18000cfc8  mov     ebx, esi
0x18000cfca  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000cfd1  jz      short loc_18000D01D
0x18000cfd3  lea     r8, aChttpconnector_7; "CHttpConnector::put_UserAgent"
0x18000cfda  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000cfe1  call    McTemplateU0s_EventWriteTransfer
0x18000cfe6  jmp     short loc_18000D01D
0x18000cfe8  cmp     ebx, 80070057h
0x18000cfee  jz      short loc_18000D002
0x18000cff0  test    ebx, ebx
0x18000cff2  jz      short loc_18000CFCA
0x18000cff4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000cffb  jz      short loc_18000D01D
0x18000cffd  mov     r9d, ebx
0x18000d000  jmp     short loc_18000D011
0x18000d002  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d009  jz      short loc_18000D01D
0x18000d00b  mov     r9d, 80070057h
0x18000d011  lea     r8, aChttpconnector_7; "CHttpConnector::put_UserAgent"
0x18000d018  call    McTemplateU0sq_EventWriteTransfer
0x18000d01d  mov     eax, ebx
0x18000d01f  mov     rbx, [rsp+38h+arg_0]
0x18000d024  add     rsp, 30h
0x18000d028  pop     rsi
0x18000d029  retn
```
