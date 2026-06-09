# BaseClearSrvActivationContextCacheNoLock

- ea: `0x180005050`
- end: `0x180005164`
- name: `BaseClearSrvActivationContextCacheNoLock`
- size: `276`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006270`

## callees

- `0x180005050`
- `0x180005580`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180005123`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180005123`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000505e`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000513e`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000505e`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000513e`

## pseudocode

```c
_QWORD *__fastcall BaseClearSrvActivationContextCacheNoLock(PRTL_AVL_TABLE Table)
{
  _QWORD *result; // rax
  _QWORD *v3; // rdx
  PVOID *v4; // rcx
  __int128 v5; // xmm0
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
    v5 = *(_OWORD *)result;
    v6 = *((_OWORD *)result + 1);
    v17 = result[22];
    v16[0] = v5;
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
    RtlDeleteElementGenericTableAvl(Table, result);
    BaseSrvActivationContextCacheFreeEntry(v16);
  }
  return result;
}

```

## disassembly

```asm
0x180005050  push    rbx
0x180005052  sub     rsp, 0E0h
0x180005059  mov     dl, 1; Restart
0x18000505b  mov     rbx, rcx
0x18000505e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180005065  nop     dword ptr [rax+rax+00h]
0x18000506a  test    rax, rax
0x18000506d  jz      loc_180005153
0x180005073  mov     rdx, [rax]
0x180005076  cmp     [rdx+8], rax
0x18000507a  jnz     loc_18000515D
0x180005080  mov     rcx, [rax+8]
0x180005084  cmp     [rcx], rax
0x180005087  jnz     loc_18000515D
0x18000508d  mov     [rcx], rdx
0x180005090  mov     [rdx+8], rcx
0x180005094  mov     rdx, rax; Buffer
0x180005097  movups  xmm0, xmmword ptr [rax]
0x18000509a  mov     rcx, [rax+0B0h]
0x1800050a1  movups  xmm1, xmmword ptr [rax+10h]
0x1800050a5  mov     [rsp+0E8h+var_18], rcx
0x1800050ad  mov     rcx, rbx; Table
0x1800050b0  movups  [rsp+0E8h+var_C8], xmm0
0x1800050b5  movups  xmm0, xmmword ptr [rax+20h]
0x1800050b9  movups  [rsp+0E8h+var_B8], xmm1
0x1800050be  movups  xmm1, xmmword ptr [rax+30h]
0x1800050c2  movups  [rsp+0E8h+var_A8], xmm0
0x1800050c7  movups  xmm0, xmmword ptr [rax+40h]
0x1800050cb  movups  [rsp+0E8h+var_98], xmm1
0x1800050d0  movups  xmm1, xmmword ptr [rax+50h]
0x1800050d4  movups  [rsp+0E8h+var_88], xmm0
0x1800050d9  movups  xmm0, xmmword ptr [rax+60h]
0x1800050dd  movups  [rsp+0E8h+var_78], xmm1
0x1800050e2  movups  xmm1, xmmword ptr [rax+70h]
0x1800050e6  movups  [rsp+0E8h+var_68], xmm0
0x1800050ee  movups  xmm0, xmmword ptr [rax+80h]
0x1800050f5  movups  [rsp+0E8h+var_58], xmm1
0x1800050fd  movups  xmm1, xmmword ptr [rax+90h]
0x180005104  movups  [rsp+0E8h+var_48], xmm0
0x18000510c  movups  xmm0, xmmword ptr [rax+0A0h]
0x180005113  movups  [rsp+0E8h+var_38], xmm1
0x18000511b  movups  [rsp+0E8h+var_28], xmm0
0x180005123  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000512a  nop     dword ptr [rax+rax+00h]
0x18000512f  lea     rcx, [rsp+0E8h+var_C8]
0x180005134  call    BaseSrvActivationContextCacheFreeEntry
0x180005139  mov     dl, 1; Restart
0x18000513b  mov     rcx, rbx; Table
0x18000513e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180005145  nop     dword ptr [rax+rax+00h]
0x18000514a  test    rax, rax
0x18000514d  jnz     loc_180005073
0x180005153  add     rsp, 0E0h
0x18000515a  pop     rbx
0x18000515b  retn
0x18000515d  mov     ecx, 3
0x180005162  int     29h; Win8: RtlFailFast(ecx)
```
