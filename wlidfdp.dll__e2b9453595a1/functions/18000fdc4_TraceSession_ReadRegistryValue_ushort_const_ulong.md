# TraceSession::ReadRegistryValue(ushort const *,ulong *)

- ea: `0x18000fdc4`
- end: `0x18000fe87`
- name: `?ReadRegistryValue@TraceSession@@AEAA_NPEBGPEAK@Z`
- size: `195`
- prototype: `char __fastcall(TraceSession *this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f11c`

## callees

- `0x18000fdc4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe77`

## pseudocode

```c
char __fastcall TraceSession::ReadRegistryValue(TraceSession *this, const unsigned __int16 *a2, unsigned int *a3)
{
  __int64 v4; // rcx
  char v6; // bl
  int v8; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+68h] [rbp+10h] BYREF
  int v10; // [rsp+6Ch] [rbp+14h]
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  v10 = HIDWORD(a2);
  v9 = 0;
  v8 = 4;
  v4 = *(_QWORD *)this;
  hKey = 0;
  v6 = 0;
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, const wchar_t *, _QWORD, int, HKEY *))(*(_QWORD *)v4 + 80LL))(
          v4,
          -2147483646,
          L"Software\\Microsoft\\IdentityCRL\\Trace",
          0,
          1,
          &hKey)
    && !(*(unsigned int (__fastcall **)(_QWORD, HKEY, const wchar_t *, _QWORD, _QWORD, unsigned int *, int *))(**(_QWORD **)this + 104LL))(
          *(_QWORD *)this,
          hKey,
          L"DisableRedaction",
          0,
          0,
          &v9,
          &v8) )
  {
    v6 = 1;
    *a3 = v9;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18000fdc4  mov     rax, rsp
0x18000fdc7  mov     [rax+10h], rdx
0x18000fdcb  push    rbx
0x18000fdcc  push    rsi
0x18000fdcd  push    rdi
0x18000fdce  sub     rsp, 40h
0x18000fdd2  mov     dword ptr [rax+10h], 0
0x18000fdd9  lea     rdx, [rsp+58h+hKey]
0x18000fdde  mov     dword ptr [rax+8], 4
0x18000fde5  mov     rsi, rcx
0x18000fde8  mov     rcx, [rcx]
0x18000fdeb  mov     rdi, r8
0x18000fdee  mov     qword ptr [rax+20h], 0
0x18000fdf6  lea     r8, aSoftwareMicros; "Software\\Microsoft\\IdentityCRL\\Trace"
0x18000fdfd  mov     [rsp+58h+var_30], rdx
0x18000fe02  xor     r9d, r9d
0x18000fe05  mov     rdx, 0FFFFFFFF80000002h
0x18000fe0c  mov     dword ptr [rsp+58h+var_38], 1
0x18000fe14  mov     rax, [rcx]
0x18000fe17  xor     bl, bl
0x18000fe19  mov     rax, [rax+50h]
0x18000fe1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe22  test    eax, eax
0x18000fe24  jnz     short loc_18000FE6D
0x18000fe26  mov     rcx, [rsi]
0x18000fe29  lea     rdx, [rsp+58h+arg_0]
0x18000fe2e  mov     [rsp+58h+var_28], rdx
0x18000fe33  lea     r8, aDisableredacti; "DisableRedaction"
0x18000fe3a  lea     rdx, [rsp+58h+arg_8]
0x18000fe3f  xor     r9d, r9d
0x18000fe42  mov     [rsp+58h+var_30], rdx
0x18000fe47  mov     rax, [rcx]
0x18000fe4a  mov     rdx, [rsp+58h+hKey]
0x18000fe4f  mov     [rsp+58h+var_38], 0
0x18000fe58  mov     rax, [rax+68h]
0x18000fe5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe61  test    eax, eax
0x18000fe63  jnz     short loc_18000FE6D
0x18000fe65  mov     eax, [rsp+58h+arg_8]
0x18000fe69  mov     bl, 1
0x18000fe6b  mov     [rdi], eax
0x18000fe6d  mov     rcx, [rsp+58h+hKey]; hKey
0x18000fe72  test    rcx, rcx
0x18000fe75  jz      short loc_18000FE7D
0x18000fe77  call    cs:__imp_RegCloseKey
0x18000fe7d  mov     al, bl
0x18000fe7f  add     rsp, 40h
0x18000fe83  pop     rdi
0x18000fe84  pop     rsi
0x18000fe85  pop     rbx
0x18000fe86  retn
```
