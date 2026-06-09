# SampSetInformationUserAndLog(void *,_USER_INFORMATION_CLASS,void *)

- ea: `0x180008a78`
- end: `0x180008b15`
- name: `?SampSetInformationUserAndLog@@YAJPEAXW4_USER_INFORMATION_CLASS@@0@Z`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008590`

## callees

- `0x1800040e0`
- `0x180006ed0`
- `0x180008a78`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180008abc`
- `ntdll!RtlNtStatusToDosError` at `0x180008ad7`
- `ntdll!RtlNtStatusToDosError` at `0x180008abc`
- `ntdll!RtlNtStatusToDosError` at `0x180008ad7`

## string_xrefs

- `0x180008ae4`: `	User comment %s not set Operation failed with code 0x%x\n`

## pseudocode

```c
__int64 __fastcall SampSetInformationUserAndLog(void *a1, __int64 a2, __int64 a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // edi
  int v7; // r8d
  ULONG v8; // eax
  ULONG v9; // eax

  if ( !a3 )
    return 3221225473LL;
  v5 = SamSetInformationUser(a1);
  v6 = v5;
  if ( v5 < 0 && SamMuiLogFile )
  {
    v7 = *(_DWORD *)(a3 + 284);
    if ( v7 == 1 )
    {
      v8 = RtlNtStatusToDosError(v5);
      fwprintf(SamMuiLogFile, L"\tUser name %s not set. Opeartion failed with code 0x%x\n", *(_QWORD *)(a3 + 56), v8);
    }
    else if ( v7 == 16 )
    {
      v9 = RtlNtStatusToDosError(v5);
      fwprintf(SamMuiLogFile, L"\tUser comment %s not set Operation failed with code 0x%x\n", *(_QWORD *)(a3 + 152), v9);
    }
    else
    {
      fwprintf(SamMuiLogFile, L"\tError: Unexpected User information field - 0x%x\n");
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180008a78  mov     [rsp+arg_0], rbx
0x180008a7d  push    rdi
0x180008a7e  sub     rsp, 20h
0x180008a82  mov     rbx, r8
0x180008a85  test    r8, r8
0x180008a88  jnz     short loc_180008A91
0x180008a8a  mov     eax, 0C0000001h
0x180008a8f  jmp     short loc_180008B0A
0x180008a91  mov     edx, 15h
0x180008a96  call    SamSetInformationUser
0x180008a9b  mov     edi, eax
0x180008a9d  test    eax, eax
0x180008a9f  jns     short loc_180008B08
0x180008aa1  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x180008aa8  test    rcx, rcx
0x180008aab  jz      short loc_180008B08
0x180008aad  mov     r8d, [rbx+11Ch]
0x180008ab4  cmp     r8d, 1
0x180008ab8  jnz     short loc_180008ACF
0x180008aba  mov     ecx, eax; Status
0x180008abc  call    cs:__imp_RtlNtStatusToDosError
0x180008ac2  mov     r8, [rbx+38h]
0x180008ac6  lea     rdx, aUserNameSNotSe; "\tUser name %s not set. Opeartion faile"...
0x180008acd  jmp     short loc_180008AEB
0x180008acf  cmp     r8d, 10h
0x180008ad3  jnz     short loc_180008AFC
0x180008ad5  mov     ecx, edi; Status
0x180008ad7  call    cs:__imp_RtlNtStatusToDosError
0x180008add  mov     r8, [rbx+98h]
0x180008ae4  lea     rdx, aUserCommentSNo; "\tUser comment %s not set Operation fai"...
0x180008aeb  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x180008af2  mov     r9d, eax
0x180008af5  call    fwprintf
0x180008afa  jmp     short loc_180008B08
0x180008afc  lea     rdx, aErrorUnexpecte; "\tError: Unexpected User information fi"...
0x180008b03  call    fwprintf
0x180008b08  mov     eax, edi
0x180008b0a  mov     rbx, [rsp+28h+arg_0]
0x180008b0f  add     rsp, 20h
0x180008b13  pop     rdi
0x180008b14  retn
```
