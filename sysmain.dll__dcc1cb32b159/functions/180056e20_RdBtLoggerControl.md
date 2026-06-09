# RdBtLoggerControl

- ea: `0x180056e20`
- end: `0x180056f3f`
- name: `RdBtLoggerControl`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180056b04`
- `0x180056dd4`

## callees

- `0x1800383e8`
- `0x18003bafc`
- `0x180056e20`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056f16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056f16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056e8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056e8e`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180056ef8`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180056ef8`

## string_xrefs

- `0x180056ec6`: `ReadyBoot`
- `0x180056eef`: `ReadyBoot`
- `0x180056e80`: `SYSTEM\CurrentControlSet\Control\WMI\AutoLogger\ReadyBoot`

## pseudocode

```c
__int64 __fastcall RdBtLoggerControl(int a1)
{
  unsigned int v2; // ebx
  ULONG v3; // eax
  BOOL v5; // [rsp+30h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-51h] BYREF
  _EVENT_TRACE_PROPERTIES Properties; // [rsp+40h] [rbp-49h] BYREF
  wchar_t pszDest[12]; // [rsp+B8h] [rbp+2Fh] BYREF

  v5 = 0;
  memset_0(&Properties, 0, 0x90u);
  hKey = 0;
  if ( a1 > 1 )
  {
    StringCbCopyW(pszDest, 0x14u, L"ReadyBoot");
    Properties.Wnode.BufferSize = 144;
    Properties.LoggerNameOffset = 120;
    v3 = ControlTraceW(0, L"ReadyBoot", &Properties, 1u);
    v2 = v3;
    if ( !v3 || v3 == 234 )
      v2 = 0;
  }
  else
  {
    v2 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Control\\WMI\\AutoLogger\\ReadyBoot",
           0,
           0x20006u,
           &hKey);
    if ( !v2 )
    {
      v5 = a1 == 0;
      v2 = PfsRegSetValue(hKey, L"Start", 4, 4, &v5);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180056e20  mov     [rsp-8+arg_0], rbx
0x180056e25  mov     [rsp-8+arg_8], rdi
0x180056e2a  push    rbp
0x180056e2b  lea     rbp, [rsp-57h]
0x180056e30  sub     rsp, 0E0h
0x180056e37  mov     rax, cs:__security_cookie
0x180056e3e  xor     rax, rsp
0x180056e41  mov     [rbp+57h+var_10], rax
0x180056e45  mov     edi, ecx
0x180056e47  mov     [rbp+57h+var_B0], 0
0x180056e4e  mov     ebx, 90h
0x180056e53  lea     rcx, [rbp+57h+Properties]; void *
0x180056e57  mov     r8d, ebx; Size
0x180056e5a  xor     edx, edx; Val
0x180056e5c  call    memset_0
0x180056e61  mov     [rbp+57h+hKey], 0
0x180056e69  cmp     edi, 1
0x180056e6c  jg      short loc_180056EC6
0x180056e6e  lea     rax, [rbp+57h+hKey]
0x180056e72  mov     r9d, 20006h; samDesired
0x180056e78  xor     r8d, r8d; ulOptions
0x180056e7b  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180056e80  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x180056e87  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180056e8e  call    cs:__imp_RegOpenKeyExW
0x180056e94  mov     ebx, eax
0x180056e96  test    eax, eax
0x180056e98  jnz     short loc_180056F0D
0x180056e9a  mov     rcx, [rbp+57h+hKey]
0x180056e9e  lea     r8d, [rbx+4]
0x180056ea2  test    edi, edi
0x180056ea4  lea     rdx, aStart; "Start"
0x180056eab  mov     r9d, r8d
0x180056eae  setz    al
0x180056eb1  mov     [rbp+57h+var_B0], eax
0x180056eb4  lea     rax, [rbp+57h+var_B0]
0x180056eb8  mov     [rsp+0E0h+phkResult], rax
0x180056ebd  call    PfsRegSetValue
0x180056ec2  mov     ebx, eax
0x180056ec4  jmp     short loc_180056F0D
0x180056ec6  lea     r8, aReadyboot; "ReadyBoot"
0x180056ecd  mov     edx, 14h; cbDest
0x180056ed2  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180056ed6  call    StringCbCopyW
0x180056edb  mov     r9d, 1; ControlCode
0x180056ee1  mov     [rbp+57h+Properties.Wnode.BufferSize], ebx
0x180056ee4  lea     r8, [rbp+57h+Properties]; Properties
0x180056ee8  mov     [rbp+57h+Properties.LoggerNameOffset], 78h ; 'x'
0x180056eef  lea     rdx, aReadyboot; "ReadyBoot"
0x180056ef6  xor     ecx, ecx; TraceHandle
0x180056ef8  call    cs:__imp_ControlTraceW
0x180056efe  mov     ebx, eax
0x180056f00  test    eax, eax
0x180056f02  jz      short loc_180056F0B
0x180056f04  cmp     eax, 0EAh
0x180056f09  jnz     short loc_180056F0D
0x180056f0b  xor     ebx, ebx
0x180056f0d  mov     rcx, [rbp+57h+hKey]; hKey
0x180056f11  test    rcx, rcx
0x180056f14  jz      short loc_180056F1C
0x180056f16  call    cs:__imp_RegCloseKey
0x180056f1c  mov     eax, ebx
0x180056f1e  mov     rcx, [rbp+57h+var_10]
0x180056f22  xor     rcx, rsp; StackCookie
0x180056f25  call    __security_check_cookie
0x180056f2a  lea     r11, [rsp+0E0h+var_s0]
0x180056f32  mov     rbx, [r11+10h]
0x180056f36  mov     rdi, [r11+18h]
0x180056f3a  mov     rsp, r11
0x180056f3d  pop     rbp
0x180056f3e  retn
```
