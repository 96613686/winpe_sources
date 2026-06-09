# UpdateNetworkLocationEntry(_SSDP_REQUEST *,ulong,_NETWORK_LOCATION_ENTRY *,int *)

- ea: `0x18000a538`
- end: `0x18000a7d4`
- name: `?UpdateNetworkLocationEntry@@YAJPEAU_SSDP_REQUEST@@KPEAU_NETWORK_LOCATION_ENTRY@@PEAH@Z`
- size: `668`
- prototype: `__int64 __fastcall(struct _SSDP_REQUEST *, unsigned int, struct _NETWORK_LOCATION_ENTRY *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180009bc0`

## callees

- `0x18000a538`
- `0x18000a844`
- `0x18000bca0`
- `0x1800271fc`
- `0x180031350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000a569`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000a604`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000a569`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000a604`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a5c7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a663`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a700`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a742`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a757`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a76d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a5c7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a663`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a700`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a742`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a757`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a76d`

## pseudocode

```c
__int64 __fastcall UpdateNetworkLocationEntry(
        struct _SSDP_REQUEST *a1,
        unsigned int a2,
        struct _NETWORK_LOCATION_ENTRY *a3,
        int *a4)
{
  __int64 v4; // rbx
  __int64 **v5; // rsi
  __int64 v9; // rdx
  void *v10; // rcx
  char *v11; // rax
  __int64 v12; // rdx
  void *v13; // rcx
  char *v14; // rax
  char *v15; // rdx
  unsigned int v16; // esi
  char *v17; // rcx
  void *v18; // rcx
  char *v19; // rax
  void *v20; // rcx
  __int64 v21; // rbp
  void *v22; // rcx
  void *v23; // rcx

  v4 = a2;
  v5 = (__int64 **)((char *)a1 + 80);
  v9 = *((_QWORD *)a3 + a2);
  if ( !v9 || (unsigned int)_o__stricmp((*v5)[6], v9) )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
        *((_QWORD *)a3 + v4),
        (*v5)[6]);
    v10 = (void *)*((_QWORD *)a3 + v4);
    *a4 = 1;
    if ( v10 )
    {
      free(v10);
      *((_QWORD *)a3 + v4) = 0;
    }
    v11 = SzaDupSza((const char *)(*v5)[6]);
    *((_QWORD *)a3 + v4) = v11;
    if ( !v11 )
      goto LABEL_26;
  }
  v12 = *((_QWORD *)a3 + v4 + 2);
  if ( !v12 || (unsigned int)_o__stricmp(**v5, v12) )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
        *((_QWORD *)a3 + v4 + 2),
        **v5);
    v13 = (void *)*((_QWORD *)a3 + v4 + 2);
    *a4 = 1;
    if ( v13 )
    {
      free(v13);
      *((_QWORD *)a3 + v4 + 2) = 0;
    }
    v14 = SzaDupSza((const char *)**v5);
    *((_QWORD *)a3 + v4 + 2) = v14;
    if ( !v14 )
      goto LABEL_26;
  }
  v15 = (char *)*((_QWORD *)a3 + v4 + 4);
  v16 = 0;
  if ( !v15 || (v17 = (char *)*((_QWORD *)a1 + 6)) == 0 || !(unsigned int)IsEqualRemoteAddress(v17, v15) )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
        *((_QWORD *)a3 + v4 + 4),
        *((_QWORD *)a1 + 6));
    v18 = (void *)*((_QWORD *)a3 + v4 + 4);
    *a4 = 1;
    if ( v18 )
    {
      free(v18);
      *((_QWORD *)a3 + v4 + 4) = 0;
    }
    v19 = SzaDupSza(*((const char **)a1 + 6));
    *((_QWORD *)a3 + v4 + 4) = v19;
    if ( !v19 )
    {
LABEL_26:
      v16 = -2147024882;
      v20 = (void *)*((_QWORD *)a3 + v4);
      v21 = v4 + 2;
      if ( v20 )
        free(v20);
      v22 = (void *)*((_QWORD *)a3 + v21);
      if ( v22 )
        free(v22);
      v23 = (void *)*((_QWORD *)a3 + v4 + 4);
      if ( v23 )
        free(v23);
      *((_QWORD *)a3 + v4) = 0;
      *((_QWORD *)a3 + v21) = 0;
      *((_QWORD *)a3 + v4 + 4) = 0;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, 2147942414LL);
    }
  }
  return v16;
}

```

## disassembly

```asm
0x18000a538  push    rbx
0x18000a53a  push    rbp
0x18000a53b  push    rsi
0x18000a53c  push    rdi
0x18000a53d  push    r14
0x18000a53f  sub     rsp, 30h
0x18000a543  mov     ebx, edx
0x18000a545  lea     rsi, [rcx+50h]
0x18000a549  mov     r14, r9
0x18000a54c  lea     rax, WPP_GLOBAL_Control
0x18000a553  mov     rdi, r8
0x18000a556  mov     rbp, rcx
0x18000a559  mov     rdx, [r8+rbx*8]
0x18000a55d  test    rdx, rdx
0x18000a560  jz      short loc_18000A580
0x18000a562  mov     rcx, [rsi]
0x18000a565  mov     rcx, [rcx+30h]
0x18000a569  call    cs:__imp__o__stricmp
0x18000a570  nop     dword ptr [rax+rax+00h]
0x18000a575  test    eax, eax
0x18000a577  jz      short loc_18000A5F4
0x18000a579  lea     rax, WPP_GLOBAL_Control
0x18000a580  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a587  cmp     rcx, rax
0x18000a58a  jz      short loc_18000A5B7
0x18000a58c  test    byte ptr [rcx+1Ch], 8
0x18000a590  jz      short loc_18000A5B7
0x18000a592  mov     rax, [rsi]
0x18000a595  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000a59c  mov     r9, [rdi+rbx*8]
0x18000a5a0  mov     edx, 0Ah
0x18000a5a5  mov     rcx, [rcx+10h]
0x18000a5a9  mov     rax, [rax+30h]
0x18000a5ad  mov     [rsp+58h+var_38], rax
0x18000a5b2  call    WPP_SF_ss
0x18000a5b7  mov     rcx, [rdi+rbx*8]; Block
0x18000a5bb  mov     dword ptr [r14], 1
0x18000a5c2  test    rcx, rcx
0x18000a5c5  jz      short loc_18000A5DB
0x18000a5c7  call    cs:__imp_free
0x18000a5ce  nop     dword ptr [rax+rax+00h]
0x18000a5d3  mov     qword ptr [rdi+rbx*8], 0
0x18000a5db  mov     rcx, [rsi]
0x18000a5de  mov     rcx, [rcx+30h]; char *
0x18000a5e2  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000a5e7  mov     [rdi+rbx*8], rax
0x18000a5eb  test    rax, rax
0x18000a5ee  jz      loc_18000A728
0x18000a5f4  mov     rdx, [rdi+rbx*8+10h]
0x18000a5f9  test    rdx, rdx
0x18000a5fc  jz      short loc_18000A614
0x18000a5fe  mov     rcx, [rsi]
0x18000a601  mov     rcx, [rcx]
0x18000a604  call    cs:__imp__o__stricmp
0x18000a60b  nop     dword ptr [rax+rax+00h]
0x18000a610  test    eax, eax
0x18000a612  jz      short loc_18000A691
0x18000a614  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a61b  lea     rax, WPP_GLOBAL_Control
0x18000a622  cmp     rcx, rax
0x18000a625  jz      short loc_18000A652
0x18000a627  test    byte ptr [rcx+1Ch], 8
0x18000a62b  jz      short loc_18000A652
0x18000a62d  mov     rax, [rsi]
0x18000a630  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000a637  mov     r9, [rdi+rbx*8+10h]
0x18000a63c  mov     edx, 0Bh
0x18000a641  mov     rcx, [rcx+10h]
0x18000a645  mov     rax, [rax]
0x18000a648  mov     [rsp+58h+var_38], rax
0x18000a64d  call    WPP_SF_ss
0x18000a652  mov     rcx, [rdi+rbx*8+10h]; Block
0x18000a657  mov     dword ptr [r14], 1
0x18000a65e  test    rcx, rcx
0x18000a661  jz      short loc_18000A678
0x18000a663  call    cs:__imp_free
0x18000a66a  nop     dword ptr [rax+rax+00h]
0x18000a66f  mov     qword ptr [rdi+rbx*8+10h], 0
0x18000a678  mov     rcx, [rsi]
0x18000a67b  mov     rcx, [rcx]; char *
0x18000a67e  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000a683  mov     [rdi+rbx*8+10h], rax
0x18000a688  test    rax, rax
0x18000a68b  jz      loc_18000A728
0x18000a691  mov     rdx, [rdi+rbx*8+20h]; String2
0x18000a696  xor     esi, esi
0x18000a698  test    rdx, rdx
0x18000a69b  jz      short loc_18000A6B3
0x18000a69d  mov     rcx, [rbp+30h]; String1
0x18000a6a1  test    rcx, rcx
0x18000a6a4  jz      short loc_18000A6B3
0x18000a6a6  call    ?IsEqualRemoteAddress@@YAHPEAD0@Z; IsEqualRemoteAddress(char *,char *)
0x18000a6ab  test    eax, eax
0x18000a6ad  jnz     loc_18000A7C6
0x18000a6b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6ba  lea     rax, WPP_GLOBAL_Control
0x18000a6c1  cmp     rcx, rax
0x18000a6c4  jz      short loc_18000A6EF
0x18000a6c6  test    byte ptr [rcx+1Ch], 8
0x18000a6ca  jz      short loc_18000A6EF
0x18000a6cc  mov     rax, [rbp+30h]
0x18000a6d0  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000a6d7  mov     r9, [rdi+rbx*8+20h]
0x18000a6dc  mov     edx, 0Ch
0x18000a6e1  mov     rcx, [rcx+10h]
0x18000a6e5  mov     [rsp+58h+var_38], rax
0x18000a6ea  call    WPP_SF_ss
0x18000a6ef  mov     rcx, [rdi+rbx*8+20h]; Block
0x18000a6f4  mov     dword ptr [r14], 1
0x18000a6fb  test    rcx, rcx
0x18000a6fe  jz      short loc_18000A711
0x18000a700  call    cs:__imp_free
0x18000a707  nop     dword ptr [rax+rax+00h]
0x18000a70c  mov     [rdi+rbx*8+20h], rsi
0x18000a711  mov     rcx, [rbp+30h]; char *
0x18000a715  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000a71a  mov     [rdi+rbx*8+20h], rax
0x18000a71f  test    rax, rax
0x18000a722  jnz     loc_18000A7C6
0x18000a728  mov     esi, 8007000Eh
0x18000a72d  mov     rcx, rbx
0x18000a730  mov     eax, 2
0x18000a735  mov     rcx, [rdi+rbx*8]; Block
0x18000a739  lea     rbp, [rax+rbx]
0x18000a73d  test    rcx, rcx
0x18000a740  jz      short loc_18000A74E
0x18000a742  call    cs:__imp_free
0x18000a749  nop     dword ptr [rax+rax+00h]
0x18000a74e  mov     rcx, [rdi+rbp*8]; Block
0x18000a752  test    rcx, rcx
0x18000a755  jz      short loc_18000A763
0x18000a757  call    cs:__imp_free
0x18000a75e  nop     dword ptr [rax+rax+00h]
0x18000a763  mov     rcx, [rdi+rbx*8+20h]; Block
0x18000a768  test    rcx, rcx
0x18000a76b  jz      short loc_18000A779
0x18000a76d  call    cs:__imp_free
0x18000a774  nop     dword ptr [rax+rax+00h]
0x18000a779  mov     qword ptr [rdi+rbx*8], 0
0x18000a781  mov     qword ptr [rdi+rbp*8], 0
0x18000a789  mov     qword ptr [rdi+rbx*8+20h], 0
0x18000a792  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a799  lea     rax, WPP_GLOBAL_Control
0x18000a7a0  cmp     rcx, rax
0x18000a7a3  jz      short loc_18000A7C6
0x18000a7a5  test    byte ptr [rcx+1Ch], 1
0x18000a7a9  jz      short loc_18000A7C6
0x18000a7ab  mov     rcx, [rcx+10h]
0x18000a7af  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000a7b6  mov     edx, 0Dh
0x18000a7bb  mov     r9d, 8007000Eh
0x18000a7c1  call    WPP_SF_d
0x18000a7c6  mov     eax, esi
0x18000a7c8  add     rsp, 30h
0x18000a7cc  pop     r14
0x18000a7ce  pop     rdi
0x18000a7cf  pop     rsi
0x18000a7d0  pop     rbp
0x18000a7d1  pop     rbx
0x18000a7d2  retn
```
