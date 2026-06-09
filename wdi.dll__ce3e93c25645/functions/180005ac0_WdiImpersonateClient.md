# WdiImpersonateClient

- ea: `0x180005ac0`
- end: `0x180005baa`
- name: `WdiImpersonateClient`
- size: `234`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002ba0`
- `0x180005ac0`

## import_xrefs

- `ntdll!NtAlpcImpersonateClientOfPort` at `0x180005b44`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x180005b44`
- `ntdll!RtlNtStatusToDosError` at `0x180005b54`
- `ntdll!RtlNtStatusToDosError` at `0x180005b54`

## string_xrefs

- `0x180005ade`: `WdiImpersonateClient`
- `0x180005b7b`: `WdiImpersonateClient`

## pseudocode

```c
__int64 __fastcall WdiImpersonateClient(__int64 a1)
{
  int v1; // r8d
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rcx
  NTSTATUS v6; // eax
  signed int Args; // ebx
  signed int v8; // eax

  if ( !a1 )
  {
    v1 = 1632;
LABEL_3:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiImpersonateClient",
      v1,
      (int)L"Error = %d",
      87);
    return 2147942487LL;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 16) - 1) <= 1 )
    return 2147946717LL;
  v3 = *(_QWORD *)(a1 + 40);
  if ( !v3 )
  {
    v1 = 1640;
    goto LABEL_3;
  }
  v4 = *(_QWORD *)(a1 + 48);
  if ( !v4 )
  {
    v1 = 1641;
    goto LABEL_3;
  }
  v5 = *(_QWORD *)(v4 + 56);
  if ( !v5 )
  {
    v1 = 1642;
    goto LABEL_3;
  }
  v6 = NtAlpcImpersonateClientOfPort(v5, v3, 0);
  if ( v6 < 0 )
  {
    v8 = RtlNtStatusToDosError(v6);
    Args = v8;
    if ( v8 > 0 )
      Args = (unsigned __int16)v8 | 0x80070000;
  }
  else
  {
    Args = 0;
  }
  if ( Args < 0 )
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiImpersonateClient",
      1648,
      (int)L"Error = %d",
      Args);
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180005ac0  sub     rsp, 38h
0x180005ac4  test    rcx, rcx
0x180005ac7  jnz     short loc_180005AFB
0x180005ac9  mov     r8d, 660h; int
0x180005acf  lea     r9, aErrorD_0; "Error = %d"
0x180005ad6  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x180005ade  lea     rdx, aWdiimpersonate_0; "WdiImpersonateClient"
0x180005ae5  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180005aec  call    WdipTraceError
0x180005af1  mov     eax, 80070057h
0x180005af6  add     rsp, 38h
0x180005afa  retn
0x180005afb  mov     eax, [rcx+10h]
0x180005afe  dec     eax
0x180005b00  cmp     eax, 1
0x180005b03  jbe     loc_180005BA0
0x180005b09  mov     rdx, [rcx+28h]
0x180005b0d  test    rdx, rdx
0x180005b10  jnz     short loc_180005B1A
0x180005b12  mov     r8d, 668h
0x180005b18  jmp     short loc_180005ACF
0x180005b1a  mov     rax, [rcx+30h]
0x180005b1e  test    rax, rax
0x180005b21  jnz     short loc_180005B2B
0x180005b23  mov     r8d, 669h
0x180005b29  jmp     short loc_180005ACF
0x180005b2b  mov     rcx, [rax+38h]
0x180005b2f  test    rcx, rcx
0x180005b32  jnz     short loc_180005B3C
0x180005b34  mov     r8d, 66Ah
0x180005b3a  jmp     short loc_180005ACF
0x180005b3c  xor     r8d, r8d
0x180005b3f  mov     [rsp+38h+var_8], rbx
0x180005b44  call    cs:__imp_NtAlpcImpersonateClientOfPort
0x180005b4a  test    eax, eax
0x180005b4c  js      short loc_180005B52
0x180005b4e  xor     ebx, ebx
0x180005b50  jmp     short loc_180005B69
0x180005b52  mov     ecx, eax; Status
0x180005b54  call    cs:__imp_RtlNtStatusToDosError
0x180005b5a  mov     ebx, eax
0x180005b5c  test    eax, eax
0x180005b5e  jle     short loc_180005B69
0x180005b60  movzx   ebx, ax
0x180005b63  or      ebx, 80070000h
0x180005b69  test    ebx, ebx
0x180005b6b  jns     short loc_180005B94
0x180005b6d  movzx   ecx, bx
0x180005b70  lea     r9, aErrorD_0; "Error = %d"
0x180005b77  mov     dword ptr [rsp+38h+Args], ecx; Args
0x180005b7b  lea     rdx, aWdiimpersonate_0; "WdiImpersonateClient"
0x180005b82  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180005b89  mov     r8d, 670h; int
0x180005b8f  call    WdipTraceError
0x180005b94  mov     eax, ebx
0x180005b96  mov     rbx, [rsp+38h+var_8]
0x180005b9b  add     rsp, 38h
0x180005b9f  retn
0x180005ba0  mov     eax, 800710DDh
0x180005ba5  add     rsp, 38h
0x180005ba9  retn
```
