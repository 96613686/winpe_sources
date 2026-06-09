# CHttpConnector::CompareProxyToLastKnownGoodProxy(ulong,ushort const *,ushort const *)

- ea: `0x18000bf80`
- end: `0x18000c00f`
- name: `?CompareProxyToLastKnownGoodProxy@CHttpConnector@@AEAAHKPEBG0@Z`
- size: `143`
- prototype: `_BOOL8 __fastcall(CHttpConnector *this, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b890`

## callees

- `0x1800024d4`
- `0x18000bf80`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bfd4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bff3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bfd4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bff3`

## string_xrefs

- `0x18000bf9d`: `CHttpConnector::CompareProxyToLastKnownGoodProxy`

## pseudocode

```c
_BOOL8 __fastcall CHttpConnector::CompareProxyToLastKnownGoodProxy(
        CHttpConnector *this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // rdx
  const WCHAR *v9; // rdx

  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(
      this,
      SDIAGPRV_EVENT_DEBUG_SUCCESS,
      "CHttpConnector::CompareProxyToLastKnownGoodProxy");
  v8 = *((_QWORD *)this + 6);
  if ( !v8 || a2 != *(_DWORD *)(v8 + 28) )
    return 0;
  v9 = *(const WCHAR **)(v8 + 32);
  if ( !a3 )
    return v9 == 0;
  if ( !v9 || lstrcmpiW(a3, v9) )
    return 0;
  v9 = *(const WCHAR **)(*((_QWORD *)this + 6) + 40LL);
  if ( !a4 )
    return v9 == 0;
  if ( !v9 )
    return 0;
  return lstrcmpiW(a4, v9) == 0;
}

```

## disassembly

```asm
0x18000bf80  push    rbx
0x18000bf82  push    rbp
0x18000bf83  push    rsi
0x18000bf84  push    rdi
0x18000bf85  sub     rsp, 28h
0x18000bf89  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000bf90  mov     rdi, r9
0x18000bf93  mov     rsi, r8
0x18000bf96  mov     ebp, edx
0x18000bf98  mov     rbx, rcx
0x18000bf9b  jz      short loc_18000BFB0
0x18000bf9d  lea     r8, aChttpconnector_3; "CHttpConnector::CompareProxyToLastKnown"...
0x18000bfa4  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000bfab  call    McTemplateU0s_EventWriteTransfer
0x18000bfb0  mov     rdx, [rbx+30h]
0x18000bfb4  test    rdx, rdx
0x18000bfb7  jz      short loc_18000BFFD
0x18000bfb9  cmp     ebp, [rdx+1Ch]
0x18000bfbc  jnz     short loc_18000BFFD
0x18000bfbe  mov     rdx, [rdx+20h]; lpString2
0x18000bfc2  test    rsi, rsi
0x18000bfc5  jnz     short loc_18000BFCC
0x18000bfc7  test    rdx, rdx
0x18000bfca  jmp     short loc_18000BFFB
0x18000bfcc  test    rdx, rdx
0x18000bfcf  jz      short loc_18000BFFD
0x18000bfd1  mov     rcx, rsi; lpString1
0x18000bfd4  call    cs:__imp_lstrcmpiW
0x18000bfda  test    eax, eax
0x18000bfdc  jnz     short loc_18000BFFD
0x18000bfde  mov     rcx, [rbx+30h]
0x18000bfe2  mov     rdx, [rcx+28h]; lpString2
0x18000bfe6  test    rdi, rdi
0x18000bfe9  jz      short loc_18000BFC7
0x18000bfeb  test    rdx, rdx
0x18000bfee  jz      short loc_18000BFFD
0x18000bff0  mov     rcx, rdi; lpString1
0x18000bff3  call    cs:__imp_lstrcmpiW
0x18000bff9  test    eax, eax
0x18000bffb  jz      short loc_18000C008
0x18000bffd  xor     eax, eax
0x18000bfff  add     rsp, 28h
0x18000c003  pop     rdi
0x18000c004  pop     rsi
0x18000c005  pop     rbp
0x18000c006  pop     rbx
0x18000c007  retn
0x18000c008  mov     eax, 1
0x18000c00d  jmp     short loc_18000BFFF
```
