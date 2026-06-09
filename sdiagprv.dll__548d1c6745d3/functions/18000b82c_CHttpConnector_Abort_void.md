# CHttpConnector::Abort(void)

- ea: `0x18000b82c`
- end: `0x18000b887`
- name: `?Abort@CHttpConnector@@QEAAJXZ`
- size: `91`
- prototype: `__int64 __fastcall(CHttpConnector *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009bc0`
- `0x180009e60`
- `0x18000c2a0`

## callees

- `0x1800024d4`
- `0x18000b82c`

## import_xrefs

- `WINHTTP!WinHttpCloseHandle` at `0x18000b83e`
- `WINHTTP!WinHttpCloseHandle` at `0x18000b855`
- `WINHTTP!WinHttpCloseHandle` at `0x18000b83e`
- `WINHTTP!WinHttpCloseHandle` at `0x18000b855`

## pseudocode

```c
__int64 __fastcall CHttpConnector::Abort(CHttpConnector *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    WinHttpCloseHandle(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    WinHttpCloseHandle(v3);
    *((_QWORD *)this + 2) = 0;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(v3, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CHttpConnector::Abort");
  return 0;
}

```

## disassembly

```asm
0x18000b82c  push    rbx
0x18000b82e  sub     rsp, 20h
0x18000b832  mov     rbx, rcx
0x18000b835  mov     rcx, [rcx+8]; hInternet
0x18000b839  test    rcx, rcx
0x18000b83c  jz      short loc_18000B84C
0x18000b83e  call    cs:__imp_WinHttpCloseHandle
0x18000b844  mov     qword ptr [rbx+8], 0
0x18000b84c  mov     rcx, [rbx+10h]; hInternet
0x18000b850  test    rcx, rcx
0x18000b853  jz      short loc_18000B863
0x18000b855  call    cs:__imp_WinHttpCloseHandle
0x18000b85b  mov     qword ptr [rbx+10h], 0
0x18000b863  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000b86a  jz      short loc_18000B87F
0x18000b86c  lea     r8, aChttpconnector; "CHttpConnector::Abort"
0x18000b873  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000b87a  call    McTemplateU0s_EventWriteTransfer
0x18000b87f  xor     eax, eax
0x18000b881  add     rsp, 20h
0x18000b885  pop     rbx
0x18000b886  retn
```
