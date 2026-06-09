# SampSetInformationAliasAndLog(void *,_ALIAS_INFORMATION_CLASS,void *)

- ea: `0x1800089d8`
- end: `0x180008a6f`
- name: `?SampSetInformationAliasAndLog@@YAJPEAXW4_ALIAS_INFORMATION_CLASS@@0@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008590`

## callees

- `0x180006ed0`
- `0x1800089d8`
- `0x180011910`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180008a16`
- `ntdll!RtlNtStatusToDosError` at `0x180008a2c`
- `ntdll!RtlNtStatusToDosError` at `0x180008a16`
- `ntdll!RtlNtStatusToDosError` at `0x180008a2c`

## string_xrefs

- `0x180008a32`: `	Alias comment  %s  not set. Operation failed with code 0x%x\n`

## pseudocode

```c
__int64 __fastcall SampSetInformationAliasAndLog(void *a1, unsigned int a2, __int64 a3)
{
  NTSTATUS v6; // eax
  unsigned int v7; // edi
  ULONG v8; // eax
  ULONG v9; // eax

  if ( !a3 )
    return 3221225473LL;
  v6 = SamSetInformationAlias(a1);
  v7 = v6;
  if ( v6 < 0 && SamMuiLogFile )
  {
    if ( a2 == 2 )
    {
      v8 = RtlNtStatusToDosError(v6);
      fwprintf(SamMuiLogFile, L"\tAlias name  %s  not set. Operation failed with code 0x%x\n", *(_QWORD *)(a3 + 8), v8);
    }
    else if ( a2 == 3 )
    {
      v9 = RtlNtStatusToDosError(v6);
      fwprintf(
        SamMuiLogFile,
        L"\tAlias comment  %s  not set. Operation failed with code 0x%x\n",
        *(_QWORD *)(a3 + 8),
        v9);
    }
    else
    {
      fwprintf(SamMuiLogFile, L"\tError: Unexpected Alias information class - 0x%x\n", a2);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800089d8  mov     [rsp+arg_0], rbx
0x1800089dd  mov     [rsp+arg_8], rsi
0x1800089e2  push    rdi
0x1800089e3  sub     rsp, 20h
0x1800089e7  mov     rsi, r8
0x1800089ea  mov     ebx, edx
0x1800089ec  test    r8, r8
0x1800089ef  jnz     short loc_1800089F8
0x1800089f1  mov     eax, 0C0000001h
0x1800089f6  jmp     short loc_180008A5F
0x1800089f8  call    SamSetInformationAlias
0x1800089fd  mov     edi, eax
0x1800089ff  test    eax, eax
0x180008a01  jns     short loc_180008A5D
0x180008a03  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x180008a0a  test    rcx, rcx
0x180008a0d  jz      short loc_180008A5D
0x180008a0f  cmp     ebx, 2
0x180008a12  jnz     short loc_180008A25
0x180008a14  mov     ecx, eax; Status
0x180008a16  call    cs:__imp_RtlNtStatusToDosError
0x180008a1c  lea     rdx, aAliasNameSNotS; "\tAlias name  %s  not set. Operation fa"...
0x180008a23  jmp     short loc_180008A39
0x180008a25  cmp     ebx, 3
0x180008a28  jnz     short loc_180008A4E
0x180008a2a  mov     ecx, edi; Status
0x180008a2c  call    cs:__imp_RtlNtStatusToDosError
0x180008a32  lea     rdx, aAliasCommentSN; "\tAlias comment  %s  not set. Operation"...
0x180008a39  mov     r8, [rsi+8]
0x180008a3d  mov     r9d, eax
0x180008a40  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x180008a47  call    fwprintf
0x180008a4c  jmp     short loc_180008A5D
0x180008a4e  mov     r8d, ebx
0x180008a51  lea     rdx, aErrorUnexpecte_0; "\tError: Unexpected Alias information c"...
0x180008a58  call    fwprintf
0x180008a5d  mov     eax, edi
0x180008a5f  mov     rbx, [rsp+28h+arg_0]
0x180008a64  mov     rsi, [rsp+28h+arg_8]
0x180008a69  add     rsp, 20h
0x180008a6d  pop     rdi
0x180008a6e  retn
```
