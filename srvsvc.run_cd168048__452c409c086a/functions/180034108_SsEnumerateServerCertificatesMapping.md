# SsEnumerateServerCertificatesMapping

- ea: `0x180034108`
- end: `0x1800341fa`
- name: `SsEnumerateServerCertificatesMapping`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001d768`

## callees

- `0x180020de8`
- `0x180034108`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003411d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003411d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003419c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003419c`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180034191`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180034191`
- `ntdll!RtlNtStatusToDosError` at `0x1800341f3`

## pseudocode

```c
ULONG __fastcall SsEnumerateServerCertificatesMapping(__int64 a1)
{
  _DWORD *v2; // rbx
  NTSTATUS RegistryValues; // edi

  v2 = LocalAlloc(0x40u, 0x70u);
  if ( v2 )
  {
    v2[2] = 16;
    *(_QWORD *)v2 = EnumerateServerCertificate;
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    v2[8] = 0;
    *((_QWORD *)v2 + 5) = 0;
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v2[16] = 0;
    *((_QWORD *)v2 + 9) = 0;
    RegistryValues = RtlQueryRegistryValuesEx(0, &word_18005E1CC, v2, a1, 0);
    LocalFree(v2);
    if ( RegistryValues >= 0 )
      return RtlNtStatusToDosError(RegistryValues);
  }
  else
  {
    RegistryValues = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids,
      (unsigned int)RegistryValues);
  }
  return RtlNtStatusToDosError(RegistryValues);
}

```

## disassembly

```asm
0x180034108  mov     [rsp+arg_0], rbx
0x18003410d  push    rdi
0x18003410e  sub     rsp, 30h
0x180034112  mov     edx, 70h ; 'p'; uBytes
0x180034117  mov     rdi, rcx
0x18003411a  lea     ecx, [rdx-30h]; uFlags
0x18003411d  call    cs:__imp_LocalAlloc
0x180034123  mov     rbx, rax
0x180034126  test    rax, rax
0x180034129  jz      short loc_1800341A8
0x18003412b  lea     rax, EnumerateServerCertificate
0x180034132  mov     dword ptr [rbx+8], 10h
0x180034139  mov     r9, rdi
0x18003413c  mov     [rbx], rax
0x18003413f  mov     r8, rbx
0x180034142  mov     qword ptr [rbx+10h], 0
0x18003414a  lea     rdx, word_18005E1CC
0x180034151  mov     qword ptr [rbx+18h], 0
0x180034159  xor     ecx, ecx
0x18003415b  mov     dword ptr [rbx+20h], 0
0x180034162  mov     qword ptr [rbx+28h], 0
0x18003416a  mov     dword ptr [rbx+30h], 0
0x180034171  mov     qword ptr [rbx+38h], 0
0x180034179  mov     dword ptr [rbx+40h], 0
0x180034180  mov     qword ptr [rbx+48h], 0
0x180034188  mov     [rsp+38h+var_18], 0
0x180034191  call    cs:__imp_RtlQueryRegistryValuesEx
0x180034197  mov     rcx, rbx; hMem
0x18003419a  mov     edi, eax
0x18003419c  call    cs:__imp_LocalFree
0x1800341a2  test    edi, edi
0x1800341a4  jns     short loc_1800341E7
0x1800341a6  jmp     short loc_1800341AD
0x1800341a8  mov     edi, 0C000009Ah
0x1800341ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800341b4  lea     rax, WPP_GLOBAL_Control
0x1800341bb  cmp     rcx, rax
0x1800341be  jz      short loc_1800341E7
0x1800341c0  test    dword ptr [rcx+1Ch], 100h
0x1800341c7  jz      short loc_1800341E7
0x1800341c9  cmp     byte ptr [rcx+19h], 1
0x1800341cd  jb      short loc_1800341E7
0x1800341cf  mov     rcx, [rcx+10h]
0x1800341d3  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800341da  mov     edx, 33h ; '3'
0x1800341df  mov     r9d, edi
0x1800341e2  call    WPP_SF_d
0x1800341e7  mov     ecx, edi
0x1800341e9  mov     rbx, [rsp+38h+arg_0]
0x1800341ee  add     rsp, 30h
0x1800341f2  pop     rdi
0x1800341f3  jmp     cs:__imp_RtlNtStatusToDosError
```
