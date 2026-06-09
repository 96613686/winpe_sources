# BaseClearSrvActivationContextCacheNoLock

- ea: `0x180004e90`
- end: `0x180004f96`
- name: `BaseClearSrvActivationContextCacheNoLock`
- size: `262`
- prototype: `_QWORD *__fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800061b0`

## callees

- `0x180004e90`
- `0x1800053a0`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004f55`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004f55`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180004e9e`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180004f70`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180004e9e`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180004f70`

## pseudocode

```c
_QWORD *__fastcall BaseClearSrvActivationContextCacheNoLock(PRTL_AVL_TABLE Table)
{
  _QWORD *result; // rax
  _QWORD *v3; // rdx
  PVOID *v4; // rcx
  __int64 v5; // rcx
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  _OWORD v16[11]; // [rsp+20h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+D0h] [rbp-18h]

  for ( result = RtlEnumerateGenericTableAvl(Table, 1u); result; result = RtlEnumerateGenericTableAvl(Table, 1u) )
  {
    v3 = (_QWORD *)*result;
    if ( *(_QWORD **)(*result + 8LL) != result || (v4 = (PVOID *)result[1], *v4 != result) )
      __fastfail(3u);
    *v4 = v3;
    v3[1] = v4;
    v5 = result[22];
    v6 = *((_OWORD *)result + 1);
    v16[0] = *(_OWORD *)result;
    v7 = *((_OWORD *)result + 2);
    v16[1] = v6;
    v8 = *((_OWORD *)result + 3);
    v16[2] = v7;
    v9 = *((_OWORD *)result + 4);
    v16[3] = v8;
    v10 = *((_OWORD *)result + 5);
    v16[4] = v9;
    v11 = *((_OWORD *)result + 6);
    v16[5] = v10;
    v12 = *((_OWORD *)result + 7);
    v16[6] = v11;
    v13 = *((_OWORD *)result + 8);
    v16[7] = v12;
    v14 = *((_OWORD *)result + 9);
    v16[8] = v13;
    v15 = *((_OWORD *)result + 10);
    v16[9] = v14;
    v16[10] = v15;
    v17 = v5;
    RtlDeleteElementGenericTableAvl(Table, result);
    BaseSrvActivationContextCacheFreeEntry((__int64)v16);
  }
  return result;
}

```

## disassembly

```asm
0x180004e90  push    rbx
0x180004e92  sub     rsp, 0E0h
0x180004e99  mov     dl, 1; Restart
0x180004e9b  mov     rbx, rcx
0x180004e9e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180004ea5  nop     dword ptr [rax+rax+00h]
0x180004eaa  test    rax, rax
0x180004ead  jz      loc_180004F85
0x180004eb3  mov     rdx, [rax]
0x180004eb6  cmp     [rdx+8], rax
0x180004eba  jnz     loc_180004F8F
0x180004ec0  mov     rcx, [rax+8]
0x180004ec4  cmp     [rcx], rax
0x180004ec7  jnz     loc_180004F8F
0x180004ecd  mov     [rcx], rdx
0x180004ed0  mov     [rdx+8], rcx
0x180004ed4  lea     rdx, [rsp+0E8h+var_C8]
0x180004ed9  movups  xmm0, xmmword ptr [rax]
0x180004edc  mov     rcx, [rax+0B0h]
0x180004ee3  movups  xmm1, xmmword ptr [rax+10h]
0x180004ee7  movups  xmmword ptr [rdx], xmm0
0x180004eea  movups  xmm0, xmmword ptr [rax+20h]
0x180004eee  movups  xmmword ptr [rdx+10h], xmm1
0x180004ef2  movups  xmm1, xmmword ptr [rax+30h]
0x180004ef6  movups  xmmword ptr [rdx+20h], xmm0
0x180004efa  movups  xmm0, xmmword ptr [rax+40h]
0x180004efe  movups  xmmword ptr [rdx+30h], xmm1
0x180004f02  movups  xmm1, xmmword ptr [rax+50h]
0x180004f06  movups  xmmword ptr [rdx+40h], xmm0
0x180004f0a  movups  xmm0, xmmword ptr [rax+60h]
0x180004f0e  movups  xmmword ptr [rdx+50h], xmm1
0x180004f12  movups  xmm1, xmmword ptr [rax+70h]
0x180004f16  movups  xmmword ptr [rdx+60h], xmm0
0x180004f1a  movups  xmm0, xmmword ptr [rax+80h]
0x180004f21  movups  xmmword ptr [rdx+70h], xmm1
0x180004f25  movups  xmm1, xmmword ptr [rax+90h]
0x180004f2c  movups  xmmword ptr [rdx+80h], xmm0
0x180004f33  movups  xmm0, xmmword ptr [rax+0A0h]
0x180004f3a  movups  xmmword ptr [rdx+90h], xmm1
0x180004f41  movups  xmmword ptr [rdx+0A0h], xmm0
0x180004f48  mov     [rdx+0B0h], rcx
0x180004f4f  mov     rdx, rax; Buffer
0x180004f52  mov     rcx, rbx; Table
0x180004f55  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180004f5c  nop     dword ptr [rax+rax+00h]
0x180004f61  lea     rcx, [rsp+0E8h+var_C8]
0x180004f66  call    BaseSrvActivationContextCacheFreeEntry
0x180004f6b  mov     dl, 1; Restart
0x180004f6d  mov     rcx, rbx; Table
0x180004f70  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180004f77  nop     dword ptr [rax+rax+00h]
0x180004f7c  test    rax, rax
0x180004f7f  jnz     loc_180004EB3
0x180004f85  add     rsp, 0E0h
0x180004f8c  pop     rbx
0x180004f8d  retn
0x180004f8f  mov     ecx, 3
0x180004f94  int     29h; Win8: RtlFailFast(ecx)
```
