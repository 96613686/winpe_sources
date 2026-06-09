# SsEnumerateStickyShares

- ea: `0x1800258f0`
- end: `0x1800259ea`
- name: `SsEnumerateStickyShares`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18002aff8`

## callees

- `0x180020de8`
- `0x1800258f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002592a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002592a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025985`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025985`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18002597a`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18002597a`
- `ntdll!RtlNtStatusToDosError` at `0x1800259d4`
- `ntdll!RtlNtStatusToDosError` at `0x1800259d4`

## pseudocode

```c
ULONG __fastcall SsEnumerateStickyShares(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rdx
  _DWORD *v4; // rbx
  NTSTATUS RegistryValues; // edi

  v1 = *(_QWORD *)(a1 + 24);
  v3 = v1 + *(unsigned int *)(a1 + 32);
  *(_QWORD *)(a1 + 12) = 0;
  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 48) = v3 & 0xFFFFFFFFFFFFFFFEuLL;
  *(_DWORD *)(a1 + 36) = 0;
  *(_QWORD *)(a1 + 40) = v1;
  v4 = LocalAlloc(0x40u, 0x70u);
  if ( v4 )
  {
    v4[2] = 16;
    *(_QWORD *)v4 = EnumerateStickyShare;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    v4[8] = 0;
    *((_QWORD *)v4 + 5) = 0;
    v4[12] = 0;
    *((_QWORD *)v4 + 7) = 0;
    v4[16] = 0;
    *((_QWORD *)v4 + 9) = 0;
    RegistryValues = RtlQueryRegistryValuesEx(0, &word_18005DDBC, v4, a1, 0);
    LocalFree(v4);
    if ( RegistryValues >= 0 )
      return 0;
  }
  else
  {
    RegistryValues = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
        (unsigned int)RegistryValues);
  }
  return RtlNtStatusToDosError(RegistryValues);
}

```

## disassembly

```asm
0x1800258f0  mov     [rsp+arg_0], rbx
0x1800258f5  mov     [rsp+arg_8], rsi
0x1800258fa  push    rdi
0x1800258fb  sub     rsp, 30h
0x1800258ff  mov     rax, [rcx+18h]
0x180025903  xor     esi, esi
0x180025905  mov     edx, [rcx+20h]
0x180025908  mov     rdi, rcx
0x18002590b  add     rdx, rax
0x18002590e  mov     [rcx+0Ch], rsi
0x180025912  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180025916  mov     [rcx+8], esi
0x180025919  mov     [rcx+30h], rdx
0x18002591d  lea     edx, [rsi+70h]; uBytes
0x180025920  mov     [rcx+24h], esi
0x180025923  mov     [rcx+28h], rax
0x180025927  lea     ecx, [rsi+40h]; uFlags
0x18002592a  call    cs:__imp_LocalAlloc
0x180025930  mov     rbx, rax
0x180025933  test    rax, rax
0x180025936  jz      short loc_180025993
0x180025938  lea     rax, EnumerateStickyShare
0x18002593f  mov     dword ptr [rbx+8], 10h
0x180025946  mov     r9, rdi
0x180025949  mov     [rbx], rax
0x18002594c  mov     r8, rbx
0x18002594f  mov     [rbx+10h], rsi
0x180025953  lea     rdx, word_18005DDBC
0x18002595a  mov     [rbx+18h], rsi
0x18002595e  xor     ecx, ecx
0x180025960  mov     [rbx+20h], esi
0x180025963  mov     [rbx+28h], rsi
0x180025967  mov     [rbx+30h], esi
0x18002596a  mov     [rbx+38h], rsi
0x18002596e  mov     [rbx+40h], esi
0x180025971  mov     [rbx+48h], rsi
0x180025975  mov     [rsp+38h+var_18], rsi
0x18002597a  call    cs:__imp_RtlQueryRegistryValuesEx
0x180025980  mov     rcx, rbx; hMem
0x180025983  mov     edi, eax
0x180025985  call    cs:__imp_LocalFree
0x18002598b  test    edi, edi
0x18002598d  js      short loc_180025998
0x18002598f  xor     eax, eax
0x180025991  jmp     short loc_1800259DA
0x180025993  mov     edi, 0C000009Ah
0x180025998  mov     rcx, cs:WPP_GLOBAL_Control
0x18002599f  lea     rax, WPP_GLOBAL_Control
0x1800259a6  cmp     rcx, rax
0x1800259a9  jz      short loc_1800259D2
0x1800259ab  test    dword ptr [rcx+1Ch], 100h
0x1800259b2  jz      short loc_1800259D2
0x1800259b4  cmp     byte ptr [rcx+19h], 1
0x1800259b8  jb      short loc_1800259D2
0x1800259ba  mov     rcx, [rcx+10h]
0x1800259be  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800259c5  mov     edx, 2Bh ; '+'
0x1800259ca  mov     r9d, edi
0x1800259cd  call    WPP_SF_d
0x1800259d2  mov     ecx, edi; Status
0x1800259d4  call    cs:__imp_RtlNtStatusToDosError
0x1800259da  mov     rbx, [rsp+38h+arg_0]
0x1800259df  mov     rsi, [rsp+38h+arg_8]
0x1800259e4  add     rsp, 30h
0x1800259e8  pop     rdi
0x1800259e9  retn
```
