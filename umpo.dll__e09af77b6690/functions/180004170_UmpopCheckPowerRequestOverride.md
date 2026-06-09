# UmpopCheckPowerRequestOverride

- ea: `0x180004170`
- end: `0x180004374`
- name: `UmpopCheckPowerRequestOverride`
- size: `516`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180003e40`
- `0x18000c534`

## callees

- `0x180002f7c`
- `0x180004170`
- `0x18000b5dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000431a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180004345`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000431a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180004345`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800041b8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180004240`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800041b8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180004240`

## string_xrefs

- `0x180004334`: `Service`

## pseudocode

```c
__int64 __fastcall UmpopCheckPowerRequestOverride(__int64 a1, int *a2)
{
  wchar_t *v2; // r12
  wchar_t *v4; // rax
  wchar_t *v5; // rbp
  unsigned int i; // edi
  char PowerRequestOverrideMask; // dl
  int v8; // esi
  unsigned __int8 v9; // bp
  __int64 result; // rax
  wchar_t *v11; // rax
  wchar_t *v12; // r13
  unsigned int j; // edi
  int v14; // eax
  __int64 v15; // rcx
  char CachedPowerRequestOverrideMask; // al
  int v17; // [rsp+60h] [rbp+8h] BYREF
  int *v18; // [rsp+68h] [rbp+10h]

  v18 = a2;
  v2 = *(wchar_t **)a1;
  v17 = 0;
  if ( *(_DWORD *)(a1 + 8) == 2 )
  {
    v15 = *(_QWORD *)(a1 + 16);
    v8 = 0;
    v9 = 0;
    if ( v15 )
    {
      CachedPowerRequestOverrideMask = UmpopGetCachedPowerRequestOverrideMask(v15, 2, &v17);
      if ( !CachedPowerRequestOverrideMask || !UmpoServiceOverrideCacheOn )
        CachedPowerRequestOverrideMask = UmpopRegistryGetPowerRequestOverrideMask(
                                           *(wchar_t **)(a1 + 16),
                                           L"Service",
                                           &v17);
      v8 = v17;
      if ( CachedPowerRequestOverrideMask )
        v9 = 1;
    }
  }
  else
  {
    if ( !*(_DWORD *)(a1 + 8) )
    {
      v4 = wcsrchr(v2, 0x5Cu);
      v5 = v2;
      if ( v4 )
        v5 = v4 + 1;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xA )
        {
          v17 = 0;
          goto LABEL_23;
        }
        if ( !UmpoDriverOverrideCacheArray[2 * i] )
          break;
        if ( !(unsigned int)_o__wcsicmp(v5) )
        {
          v17 = dword_1800249E8[4 * i];
          break;
        }
      }
      PowerRequestOverrideMask = 1;
      if ( UmpoDriverOverrideCacheOn )
        goto LABEL_9;
LABEL_23:
      PowerRequestOverrideMask = UmpopRegistryGetPowerRequestOverrideMask(v2, L"Driver", &v17);
LABEL_9:
      v8 = 0;
      v9 = 0;
      goto LABEL_10;
    }
    v8 = 0;
    v9 = 0;
  }
  v11 = wcsrchr(v2, 0x5Cu);
  v12 = v2;
  if ( v11 )
    v12 = v11 + 1;
  for ( j = 0; ; ++j )
  {
    if ( j >= 0xA )
    {
      v17 = 0;
      goto LABEL_30;
    }
    if ( !UmpoProcessOverrideCacheArray[2 * j] )
    {
      v14 = 0;
      goto LABEL_20;
    }
    if ( !(unsigned int)_o__wcsicmp(v12) )
      break;
  }
  v14 = dword_180024928[4 * j];
LABEL_20:
  PowerRequestOverrideMask = 1;
  v17 = v14;
  if ( UmpoProcessOverrideCacheOn )
    goto LABEL_10;
LABEL_30:
  PowerRequestOverrideMask = UmpopRegistryGetPowerRequestOverrideMask(v2, L"Process", &v17);
LABEL_10:
  result = v9;
  if ( PowerRequestOverrideMask )
    result = 1;
  *v18 = v8 | v17;
  return result;
}

```

## disassembly

```asm
0x180004170  mov     [rsp+arg_10], rbx
0x180004175  mov     [rsp+arg_8], rdx
0x18000417a  push    rbp
0x18000417b  push    rsi
0x18000417c  push    rdi
0x18000417d  push    r12
0x18000417f  push    r13
0x180004181  push    r14
0x180004183  push    r15
0x180004185  sub     rsp, 20h
0x180004189  mov     r12, [rcx]
0x18000418c  mov     ebx, 1
0x180004191  mov     rdi, rcx
0x180004194  mov     [rsp+58h+arg_0], 0
0x18000419c  lea     edx, [rbx+1]
0x18000419f  cmp     [rcx+8], edx
0x1800041a2  jz      loc_1800042B7
0x1800041a8  cmp     dword ptr [rcx+8], 0
0x1800041ac  jnz     loc_180004233
0x1800041b2  lea     edx, [rbx+5Bh]; Ch
0x1800041b5  mov     rcx, r12; Str
0x1800041b8  call    cs:__imp_wcsrchr
0x1800041be  mov     rbp, r12
0x1800041c1  lea     r14, __ImageBase
0x1800041c8  test    rax, rax
0x1800041cb  lea     rcx, [rax+2]
0x1800041cf  cmovnz  rbp, rcx
0x1800041d3  xor     edi, edi
0x1800041d5  cmp     edi, 0Ah
0x1800041d8  jnb     loc_180004294
0x1800041de  mov     esi, edi
0x1800041e0  add     rsi, rsi
0x1800041e3  mov     rdx, rva UmpoDriverOverrideCacheArray[r14+rsi*8]
0x1800041eb  test    rdx, rdx
0x1800041ee  jnz     loc_180004317
0x1800041f4  cmp     cs:UmpoDriverOverrideCacheOn, 0
0x1800041fb  mov     dl, bl
0x1800041fd  jz      loc_18000429C
0x180004203  xor     esi, esi
0x180004205  xor     bpl, bpl
0x180004208  mov     ecx, [rsp+58h+arg_0]
0x18000420c  or      ecx, esi
0x18000420e  movzx   eax, bpl
0x180004212  test    dl, dl
0x180004214  mov     rdx, [rsp+58h+arg_8]
0x180004219  cmovnz  eax, ebx
0x18000421c  mov     rbx, [rsp+58h+arg_10]
0x180004221  mov     [rdx], ecx
0x180004223  add     rsp, 20h
0x180004227  pop     r15
0x180004229  pop     r14
0x18000422b  pop     r13
0x18000422d  pop     r12
0x18000422f  pop     rdi
0x180004230  pop     rsi
0x180004231  pop     rbp
0x180004232  retn
0x180004233  xor     esi, esi
0x180004235  xor     bpl, bpl
0x180004238  mov     edx, 5Ch ; '\'; Ch
0x18000423d  mov     rcx, r12; Str
0x180004240  call    cs:__imp_wcsrchr
0x180004246  mov     r13, r12
0x180004249  lea     r14, __ImageBase
0x180004250  test    rax, rax
0x180004253  lea     rcx, [rax+2]
0x180004257  cmovnz  r13, rcx
0x18000425b  xor     edi, edi
0x18000425d  cmp     edi, 0Ah
0x180004260  jnb     loc_1800042F4
0x180004266  mov     r15d, edi
0x180004269  add     r15, r15
0x18000426c  mov     rdx, rva UmpoProcessOverrideCacheArray[r14+r15*8]
0x180004274  test    rdx, rdx
0x180004277  jnz     loc_180004342
0x18000427d  xor     eax, eax
0x18000427f  cmp     cs:UmpoProcessOverrideCacheOn, 0
0x180004286  mov     dl, bl
0x180004288  mov     [rsp+58h+arg_0], eax
0x18000428c  jnz     loc_180004208
0x180004292  jmp     short loc_1800042FC
0x180004294  mov     [rsp+58h+arg_0], 0
0x18000429c  lea     r8, [rsp+58h+arg_0]
0x1800042a1  mov     rcx, r12; Str
0x1800042a4  lea     rdx, aDriver; "Driver"
0x1800042ab  call    UmpopRegistryGetPowerRequestOverrideMask
0x1800042b0  mov     dl, al
0x1800042b2  jmp     loc_180004203
0x1800042b7  mov     rcx, [rcx+10h]
0x1800042bb  xor     esi, esi
0x1800042bd  xor     bpl, bpl
0x1800042c0  test    rcx, rcx
0x1800042c3  jz      loc_180004238
0x1800042c9  lea     r8, [rsp+58h+arg_0]
0x1800042ce  call    UmpopGetCachedPowerRequestOverrideMask
0x1800042d3  test    al, al
0x1800042d5  jz      short loc_18000432B
0x1800042d7  cmp     cs:UmpoServiceOverrideCacheOn, sil
0x1800042de  jz      short loc_18000432B
0x1800042e0  mov     esi, [rsp+58h+arg_0]
0x1800042e4  test    al, al
0x1800042e6  jz      loc_180004238
0x1800042ec  mov     bpl, bl
0x1800042ef  jmp     loc_180004238
0x1800042f4  mov     [rsp+58h+arg_0], 0
0x1800042fc  lea     r8, [rsp+58h+arg_0]
0x180004301  mov     rcx, r12; Str
0x180004304  lea     rdx, aProcess; "Process"
0x18000430b  call    UmpopRegistryGetPowerRequestOverrideMask
0x180004310  mov     dl, al
0x180004312  jmp     loc_180004208
0x180004317  mov     rcx, rbp
0x18000431a  call    cs:__imp__o__wcsicmp
0x180004320  test    eax, eax
0x180004322  jz      short loc_180004356
0x180004324  add     edi, ebx
0x180004326  jmp     loc_1800041D5
0x18000432b  mov     rcx, [rdi+10h]; Str
0x18000432f  lea     r8, [rsp+58h+arg_0]
0x180004334  lea     rdx, aService_0; "Service"
0x18000433b  call    UmpopRegistryGetPowerRequestOverrideMask
0x180004340  jmp     short loc_1800042E0
0x180004342  mov     rcx, r13
0x180004345  call    cs:__imp__o__wcsicmp
0x18000434b  test    eax, eax
0x18000434d  jz      short loc_180004367
0x18000434f  add     edi, ebx
0x180004351  jmp     loc_18000425D
0x180004356  mov     eax, rva dword_1800249E8[r14+rsi*8]
0x18000435e  mov     [rsp+58h+arg_0], eax
0x180004362  jmp     loc_1800041F4
0x180004367  mov     eax, rva dword_180024928[r14+r15*8]
0x18000436f  jmp     loc_18000427F
```
