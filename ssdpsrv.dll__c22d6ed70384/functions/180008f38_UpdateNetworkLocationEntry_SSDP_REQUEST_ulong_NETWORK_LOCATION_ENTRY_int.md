# UpdateNetworkLocationEntry(_SSDP_REQUEST *,ulong,_NETWORK_LOCATION_ENTRY *,int *)

- ea: `0x180008f38`
- end: `0x1800091a3`
- name: `?UpdateNetworkLocationEntry@@YAJPEAU_SSDP_REQUEST@@KPEAU_NETWORK_LOCATION_ENTRY@@PEAH@Z`
- size: `619`
- prototype: `__int64 __fastcall(struct _SSDP_REQUEST *, unsigned int, struct _NETWORK_LOCATION_ENTRY *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180008610`

## callees

- `0x180008f38`
- `0x18000920c`
- `0x18000a50c`
- `0x1800255a8`
- `0x18002f0f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180008f69`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180008ff8`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180008f69`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180008ff8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008fc1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009051`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800090e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009124`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009133`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009143`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008fc1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009051`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800090e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009124`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009133`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009143`

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
0x180008f38  push    rbx
0x180008f3a  push    rbp
0x180008f3b  push    rsi
0x180008f3c  push    rdi
0x180008f3d  push    r14
0x180008f3f  sub     rsp, 30h
0x180008f43  mov     ebx, edx
0x180008f45  lea     rsi, [rcx+50h]
0x180008f49  mov     r14, r9
0x180008f4c  lea     rax, WPP_GLOBAL_Control
0x180008f53  mov     rdi, r8
0x180008f56  mov     rbp, rcx
0x180008f59  mov     rdx, [r8+rbx*8]
0x180008f5d  test    rdx, rdx
0x180008f60  jz      short loc_180008F7A
0x180008f62  mov     rcx, [rsi]
0x180008f65  mov     rcx, [rcx+30h]
0x180008f69  call    cs:__imp__o__stricmp
0x180008f6f  test    eax, eax
0x180008f71  jz      short loc_180008FE8
0x180008f73  lea     rax, WPP_GLOBAL_Control
0x180008f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f81  cmp     rcx, rax
0x180008f84  jz      short loc_180008FB1
0x180008f86  test    byte ptr [rcx+1Ch], 8
0x180008f8a  jz      short loc_180008FB1
0x180008f8c  mov     rax, [rsi]
0x180008f8f  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180008f96  mov     r9, [rdi+rbx*8]
0x180008f9a  mov     edx, 0Ah
0x180008f9f  mov     rcx, [rcx+10h]
0x180008fa3  mov     rax, [rax+30h]
0x180008fa7  mov     [rsp+58h+var_38], rax
0x180008fac  call    WPP_SF_ss
0x180008fb1  mov     rcx, [rdi+rbx*8]; Block
0x180008fb5  mov     dword ptr [r14], 1
0x180008fbc  test    rcx, rcx
0x180008fbf  jz      short loc_180008FCF
0x180008fc1  call    cs:__imp_free
0x180008fc7  mov     qword ptr [rdi+rbx*8], 0
0x180008fcf  mov     rcx, [rsi]
0x180008fd2  mov     rcx, [rcx+30h]; char *
0x180008fd6  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x180008fdb  mov     [rdi+rbx*8], rax
0x180008fdf  test    rax, rax
0x180008fe2  jz      loc_18000910A
0x180008fe8  mov     rdx, [rdi+rbx*8+10h]
0x180008fed  test    rdx, rdx
0x180008ff0  jz      short loc_180009002
0x180008ff2  mov     rcx, [rsi]
0x180008ff5  mov     rcx, [rcx]
0x180008ff8  call    cs:__imp__o__stricmp
0x180008ffe  test    eax, eax
0x180009000  jz      short loc_180009079
0x180009002  mov     rcx, cs:WPP_GLOBAL_Control
0x180009009  lea     rax, WPP_GLOBAL_Control
0x180009010  cmp     rcx, rax
0x180009013  jz      short loc_180009040
0x180009015  test    byte ptr [rcx+1Ch], 8
0x180009019  jz      short loc_180009040
0x18000901b  mov     rax, [rsi]
0x18000901e  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180009025  mov     r9, [rdi+rbx*8+10h]
0x18000902a  mov     edx, 0Bh
0x18000902f  mov     rcx, [rcx+10h]
0x180009033  mov     rax, [rax]
0x180009036  mov     [rsp+58h+var_38], rax
0x18000903b  call    WPP_SF_ss
0x180009040  mov     rcx, [rdi+rbx*8+10h]; Block
0x180009045  mov     dword ptr [r14], 1
0x18000904c  test    rcx, rcx
0x18000904f  jz      short loc_180009060
0x180009051  call    cs:__imp_free
0x180009057  mov     qword ptr [rdi+rbx*8+10h], 0
0x180009060  mov     rcx, [rsi]
0x180009063  mov     rcx, [rcx]; char *
0x180009066  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18000906b  mov     [rdi+rbx*8+10h], rax
0x180009070  test    rax, rax
0x180009073  jz      loc_18000910A
0x180009079  mov     rdx, [rdi+rbx*8+20h]; String2
0x18000907e  xor     esi, esi
0x180009080  test    rdx, rdx
0x180009083  jz      short loc_18000909B
0x180009085  mov     rcx, [rbp+30h]; String1
0x180009089  test    rcx, rcx
0x18000908c  jz      short loc_18000909B
0x18000908e  call    ?IsEqualRemoteAddress@@YAHPEAD0@Z; IsEqualRemoteAddress(char *,char *)
0x180009093  test    eax, eax
0x180009095  jnz     loc_180009196
0x18000909b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090a2  lea     rax, WPP_GLOBAL_Control
0x1800090a9  cmp     rcx, rax
0x1800090ac  jz      short loc_1800090D7
0x1800090ae  test    byte ptr [rcx+1Ch], 8
0x1800090b2  jz      short loc_1800090D7
0x1800090b4  mov     rax, [rbp+30h]
0x1800090b8  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x1800090bf  mov     r9, [rdi+rbx*8+20h]
0x1800090c4  mov     edx, 0Ch
0x1800090c9  mov     rcx, [rcx+10h]
0x1800090cd  mov     [rsp+58h+var_38], rax
0x1800090d2  call    WPP_SF_ss
0x1800090d7  mov     rcx, [rdi+rbx*8+20h]; Block
0x1800090dc  mov     dword ptr [r14], 1
0x1800090e3  test    rcx, rcx
0x1800090e6  jz      short loc_1800090F3
0x1800090e8  call    cs:__imp_free
0x1800090ee  mov     [rdi+rbx*8+20h], rsi
0x1800090f3  mov     rcx, [rbp+30h]; char *
0x1800090f7  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x1800090fc  mov     [rdi+rbx*8+20h], rax
0x180009101  test    rax, rax
0x180009104  jnz     loc_180009196
0x18000910a  mov     esi, 8007000Eh
0x18000910f  mov     rcx, rbx
0x180009112  mov     eax, 2
0x180009117  mov     rcx, [rdi+rbx*8]; Block
0x18000911b  lea     rbp, [rax+rbx]
0x18000911f  test    rcx, rcx
0x180009122  jz      short loc_18000912A
0x180009124  call    cs:__imp_free
0x18000912a  mov     rcx, [rdi+rbp*8]; Block
0x18000912e  test    rcx, rcx
0x180009131  jz      short loc_180009139
0x180009133  call    cs:__imp_free
0x180009139  mov     rcx, [rdi+rbx*8+20h]; Block
0x18000913e  test    rcx, rcx
0x180009141  jz      short loc_180009149
0x180009143  call    cs:__imp_free
0x180009149  mov     qword ptr [rdi+rbx*8], 0
0x180009151  mov     qword ptr [rdi+rbp*8], 0
0x180009159  mov     qword ptr [rdi+rbx*8+20h], 0
0x180009162  mov     rcx, cs:WPP_GLOBAL_Control
0x180009169  lea     rax, WPP_GLOBAL_Control
0x180009170  cmp     rcx, rax
0x180009173  jz      short loc_180009196
0x180009175  test    byte ptr [rcx+1Ch], 1
0x180009179  jz      short loc_180009196
0x18000917b  mov     rcx, [rcx+10h]
0x18000917f  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180009186  mov     edx, 0Dh
0x18000918b  mov     r9d, 8007000Eh
0x180009191  call    WPP_SF_d
0x180009196  mov     eax, esi
0x180009198  add     rsp, 30h
0x18000919c  pop     r14
0x18000919e  pop     rdi
0x18000919f  pop     rsi
0x1800091a0  pop     rbp
0x1800091a1  pop     rbx
0x1800091a2  retn
```
