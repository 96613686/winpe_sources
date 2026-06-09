# AllowServiceAccessWithNoReaders(void)

- ea: `0x180002030`
- end: `0x1800020aa`
- name: `?AllowServiceAccessWithNoReaders@@YA_NXZ`
- size: `122`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007f40`

## callees

- `0x180002030`
- `0x1800020b0`
- `0x180002180`
- `0x180002220`

## string_xrefs

- `0x180002072`: `AllowServiceAccessWithNoReaders`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool AllowServiceAccessWithNoReaders(void)
{
  unsigned int *v0; // r9
  unsigned int v1; // ebx
  unsigned int v3; // [rsp+30h] [rbp-48h]
  _DWORD phkResult[16]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v6; // [rsp+80h] [rbp+8h] BYREF

  try
  {
    CRegistry::CRegistry(
      phkResult,
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Cryptography\\Calais",
      0x20019u,
      0xFFFFFFE0);
    v6 = 0;
    CRegistry::GetValue((CRegistry *)phkResult, L"AllowServiceAccessWithNoReaders", &v6, v0);
    v1 = v6;
    v3 = v6;
    CRegistry::~CRegistry((CRegistry *)phkResult);
  }
  catch ( ... )
  {
    v1 = v3;
  }
  return v1 != 0;
}

```

## disassembly

```asm
0x180002030  push    rbx
0x180002032  sub     rsp, 70h
0x180002036  xor     ebx, ebx
0x180002038  mov     [rsp+78h+var_48], ebx
0x18000203c  mov     [rsp+78h+dwOptions], 0FFFFFFE0h; dwOptions
0x180002044  mov     r9d, 20019h; samDesired
0x18000204a  mov     r8, cs:lpSubKey; lpSubKey
0x180002051  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180002058  lea     rcx, [rsp+78h+phkResult]; phkResult
0x18000205d  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::CRegistry(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x180002062  nop
0x180002063  mov     [rsp+78h+arg_0], ebx
0x18000206a  lea     r8, [rsp+78h+arg_0]; unsigned int *
0x180002072  lea     rdx, aAllowserviceac; "AllowServiceAccessWithNoReaders"
0x180002079  lea     rcx, [rsp+78h+phkResult]; this
0x18000207e  call    ?GetValue@CRegistry@@QEBAXPEBGPEAK1@Z; CRegistry::GetValue(ushort const *,ulong *,ulong *)
0x180002083  mov     ebx, [rsp+78h+arg_0]
0x18000208a  mov     [rsp+78h+var_48], ebx
0x18000208e  lea     rcx, [rsp+78h+phkResult]; this
0x180002093  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x180002098  nop
0x180002099  test    ebx, ebx
0x18000209b  setnz   al
0x18000209e  add     rsp, 70h
0x1800020a2  pop     rbx
0x1800020a3  retn
0x1800020a4  mov     ebx, [rsp+78h+var_48]
0x1800020a8  jmp     short loc_180002099
```
