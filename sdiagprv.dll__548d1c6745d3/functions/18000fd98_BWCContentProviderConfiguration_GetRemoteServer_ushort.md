# BWCContentProviderConfiguration::GetRemoteServer(ushort * *)

- ea: `0x18000fd98`
- end: `0x18000fe5a`
- name: `?GetRemoteServer@BWCContentProviderConfiguration@@QEBAJPEAPEAG@Z`
- size: `194`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009e60`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180002ac4`
- `0x18000fd98`

## string_xrefs

- `0x18000fdc2`: `BWCContentProviderConfiguration::GetRemoteServer`
- `0x18000fe05`: `BWCContentProviderConfiguration::GetRemoteServer`
- `0x18000fe46`: `BWCContentProviderConfiguration::GetRemoteServer`

## pseudocode

```c
__int64 __fastcall BWCContentProviderConfiguration::GetRemoteServer(
        const unsigned __int16 **this,
        unsigned __int16 **a2)
{
  unsigned int v2; // ebx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 *v7; // rdx

  if ( a2 )
  {
    *a2 = 0;
    v3 = SDiagPrviCopyPWSTR(this[1], a2);
    v2 = v3;
    if ( v3 == -2147024882 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return v2;
      v7 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    }
    else
    {
      if ( v3 == -2147024809 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          return v2;
        v6 = 2147942487LL;
        goto LABEL_9;
      }
      if ( v3 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          return v2;
        v6 = v3;
LABEL_9:
        McTemplateU0sq_EventWriteTransfer(v5, v4, "BWCContentProviderConfiguration::GetRemoteServer", v6);
        return v2;
      }
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
        return v2;
      v7 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
    }
    McTemplateU0s_EventWriteTransfer(v5, v7, "BWCContentProviderConfiguration::GetRemoteServer");
    return v2;
  }
  v2 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      0,
      (unsigned int)"BWCContentProviderConfiguration::GetRemoteServer",
      -2147024809,
      (__int64)"RemoteServer");
  return v2;
}

```

## disassembly

```asm
0x18000fd98  push    rbx
0x18000fd9a  sub     rsp, 30h
0x18000fd9e  test    rdx, rdx
0x18000fda1  jnz     short loc_18000FDD5
0x18000fda3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fdaa  mov     ebx, 80070057h
0x18000fdaf  jz      loc_18000FE52
0x18000fdb5  lea     rax, aRemoteserver; "RemoteServer"
0x18000fdbc  mov     r9d, 80070057h
0x18000fdc2  lea     r8, aBwccontentprov_6; "BWCContentProviderConfiguration::GetRem"...
0x18000fdc9  mov     [rsp+38h+var_18], rax
0x18000fdce  call    McTemplateU0sqs_EventWriteTransfer
0x18000fdd3  jmp     short loc_18000FE52
0x18000fdd5  mov     qword ptr [rdx], 0
0x18000fddc  mov     rcx, [rcx+8]; unsigned __int16 *
0x18000fde0  call    ?SDiagPrviCopyPWSTR@@YAJPEBGPEAPEAG@Z; SDiagPrviCopyPWSTR(ushort const *,ushort * *)
0x18000fde5  mov     ebx, eax
0x18000fde7  cmp     eax, 8007000Eh
0x18000fdec  jz      short loc_18000FE36
0x18000fdee  cmp     eax, 80070057h
0x18000fdf3  jz      short loc_18000FE25
0x18000fdf5  test    eax, eax
0x18000fdf7  jz      short loc_18000FE13
0x18000fdf9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fe00  jz      short loc_18000FE52
0x18000fe02  mov     r9d, eax
0x18000fe05  lea     r8, aBwccontentprov_6; "BWCContentProviderConfiguration::GetRem"...
0x18000fe0c  call    McTemplateU0sq_EventWriteTransfer
0x18000fe11  jmp     short loc_18000FE52
0x18000fe13  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000fe1a  jz      short loc_18000FE52
0x18000fe1c  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000fe23  jmp     short loc_18000FE46
0x18000fe25  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fe2c  jz      short loc_18000FE52
0x18000fe2e  mov     r9d, 80070057h
0x18000fe34  jmp     short loc_18000FE05
0x18000fe36  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fe3d  jz      short loc_18000FE52
0x18000fe3f  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000fe46  lea     r8, aBwccontentprov_6; "BWCContentProviderConfiguration::GetRem"...
0x18000fe4d  call    McTemplateU0s_EventWriteTransfer
0x18000fe52  mov     eax, ebx
0x18000fe54  add     rsp, 30h
0x18000fe58  pop     rbx
0x18000fe59  retn
```
