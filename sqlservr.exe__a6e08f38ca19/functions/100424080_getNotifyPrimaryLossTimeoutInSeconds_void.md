# getNotifyPrimaryLossTimeoutInSeconds(void)

- ea: `0x100424080`
- end: `0x100424107`
- name: `?getNotifyPrimaryLossTimeoutInSeconds@@YAKXZ`
- size: `135`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x100424110`

## callees

- `0x100424080`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1004240eb`
- `KERNEL32!HeapFree` at `0x1004240eb`
- `KERNEL32!GetProcessHeap` at `0x1004240dd`
- `KERNEL32!GetProcessHeap` at `0x1004240dd`
- `api-ms-win-crt-convert-l1-1-0!wcstoul` at `0x1004240cc`
- `api-ms-win-crt-convert-l1-1-0!wcstoul` at `0x1004240cc`
- `hostregdll!HostReg_ReadConfigurationSetting` at `0x1004240ae`
- `hostregdll!HostReg_ReadConfigurationSetting` at `0x1004240ae`

## string_xrefs

- `0x1004240a7`: `SQL.Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 getNotifyPrimaryLossTimeoutInSeconds(void)
{
  const wchar_t *v0; // rax
  wchar_t *v1; // rbx
  unsigned int v2; // edi
  HANDLE ProcessHeap; // rax
  int v5; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *v6; // [rsp+48h] [rbp+10h]

  v0 = (const wchar_t *)HostReg_ReadConfigurationSetting(
                          L"SQL.Config",
                          L"SQL",
                          L"NotifyPrimaryLossTimeoutInSeconds",
                          &v5);
  v1 = (wchar_t *)v0;
  v6 = v0;
  v2 = 0;
  if ( v5 >= 0 )
    v2 = 1000 * wcstoul(v0, 0, 0);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    v6 = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x100424080  push    rdi
0x100424082  sub     rsp, 30h
0x100424086  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10042408f  mov     [rsp+38h+arg_10], rbx
0x100424094  lea     r9, [rsp+38h+arg_0]
0x100424099  lea     r8, aNotifyprimaryl_0; "NotifyPrimaryLossTimeoutInSeconds"
0x1004240a0  lea     rdx, aSql; "SQL"
0x1004240a7  lea     rcx, aSqlConfig; "SQL.Config"
0x1004240ae  call    cs:__imp_HostReg_ReadConfigurationSetting
0x1004240b4  mov     rbx, rax
0x1004240b7  mov     [rsp+38h+arg_8], rax
0x1004240bc  xor     edi, edi
0x1004240be  cmp     [rsp+38h+arg_0], edi
0x1004240c2  jl      short loc_1004240D8
0x1004240c4  xor     r8d, r8d; Radix
0x1004240c7  xor     edx, edx; EndPtr
0x1004240c9  mov     rcx, rax; String
0x1004240cc  call    cs:__imp_wcstoul
0x1004240d2  imul    edi, eax, 3E8h
0x1004240d8  test    rbx, rbx
0x1004240db  jz      short loc_1004240FA
0x1004240dd  call    cs:__imp_GetProcessHeap
0x1004240e3  mov     rcx, rax; hHeap
0x1004240e6  mov     r8, rbx; lpMem
0x1004240e9  xor     edx, edx; dwFlags
0x1004240eb  call    cs:__imp_HeapFree
0x1004240f1  mov     [rsp+38h+arg_8], 0
0x1004240fa  mov     eax, edi
0x1004240fc  mov     rbx, [rsp+38h+arg_10]
0x100424101  add     rsp, 30h
0x100424105  pop     rdi
0x100424106  retn
```
