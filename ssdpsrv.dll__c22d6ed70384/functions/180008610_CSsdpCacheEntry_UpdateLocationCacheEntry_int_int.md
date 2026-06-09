# CSsdpCacheEntry::UpdateLocationCacheEntry(int *,int *)

- ea: `0x180008610`
- end: `0x180008925`
- name: `?UpdateLocationCacheEntry@CSsdpCacheEntry@@AEAAJPEAH0@Z`
- size: `789`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, int *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180005740`
- `0x180015c78`

## callees

- `0x180008610`
- `0x180008e10`
- `0x180008f38`
- `0x1800255a8`
- `0x1800260c8`
- `0x18002735c`
- `0x18002dcf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008806`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008806`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180008841`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180008841`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::UpdateLocationCacheEntry(CSsdpCacheEntry *this, int *a2, int *a3)
{
  _QWORD *v3; // rax
  char ***v7; // rsi
  unsigned int LocationHeaderAddressFamily; // ebp
  unsigned int v9; // r9d
  unsigned int v10; // edx
  unsigned __int64 v11; // r8
  __int64 v12; // rax
  int updated; // eax
  unsigned int v14; // ebx
  LPCSTR v15; // rcx
  __int64 v16; // rdx
  __int64 v18; // rcx
  void *v19; // rax
  __int64 v20; // rax
  void *v21; // rcx
  __int128 v22; // xmm0
  __int128 v23; // [rsp+20h] [rbp-48h]
  int v24; // [rsp+70h] [rbp+8h] BYREF

  v3 = (_QWORD *)*((_QWORD *)this + 11);
  v24 = 0;
  if ( !v3[6] || !*v3 )
  {
    v14 = -2147024809;
LABEL_32:
    v15 = WPP_GLOBAL_Control;
LABEL_33:
    if ( v15 != (LPCSTR)&WPP_GLOBAL_Control && (v15[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v15 + 2), 20, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v14);
    return v14;
  }
  v7 = (char ***)((char *)this + 8);
  if ( this == (CSsdpCacheEntry *)-8LL )
  {
    LocationHeaderAddressFamily = 0;
  }
  else
  {
    LocationHeaderAddressFamily = GetLocationHeaderAddressFamily(*(LPSTR *)(*((_QWORD *)this + 11) + 48LL));
    if ( !LocationHeaderAddressFamily )
      LocationHeaderAddressFamily = GetHostHeaderAddressFamily(*v7[10]);
  }
  v9 = *((_DWORD *)this + 26);
  v10 = 0;
  v23 = *(_OWORD *)((char *)this + 40);
  while ( 1 )
  {
    if ( v10 >= v9 )
      goto LABEL_37;
    v11 = *((_QWORD *)this + 12) + ((unsigned __int64)v10 << 6);
    v12 = *(_QWORD *)(v11 + 48) - v23;
    if ( !v12 )
      v12 = *(_QWORD *)(v11 + 56) - *((_QWORD *)&v23 + 1);
    if ( !v12 )
      break;
    ++v10;
  }
  if ( !v11 )
  {
LABEL_37:
    v18 = *((_QWORD *)this + 12);
    if ( v18 )
    {
      v20 = _o_realloc(v18, (unsigned __int64)(v9 + 1) << 6);
      if ( !v20 )
      {
        v14 = -2147024882;
        goto LABEL_32;
      }
      v21 = (void *)(v20 + ((unsigned __int64)*((unsigned int *)this + 26) << 6));
      *((_QWORD *)this + 12) = v20;
      memset_0(v21, 0, 0x40u);
      v11 = *((_QWORD *)this + 12) + ((unsigned __int64)(unsigned int)(*((_DWORD *)this + 26))++ << 6);
    }
    else
    {
      v19 = malloc(0x40u);
      *((_QWORD *)this + 12) = v19;
      if ( !v19 )
      {
        v14 = -2147024882;
        goto LABEL_32;
      }
      *((_DWORD *)this + 26) = 1;
      memset_0(v19, 0, 0x40u);
      v11 = *((_QWORD *)this + 12);
    }
    v22 = *(_OWORD *)((char *)this + 40);
    v24 = 1;
    *(_OWORD *)(v11 + 48) = v22;
  }
  if ( LocationHeaderAddressFamily == 1 )
  {
    updated = UpdateNetworkLocationEntry((struct _SSDP_REQUEST *)v7, 0, (struct _NETWORK_LOCATION_ENTRY *)v11, &v24);
    v14 = updated;
    if ( updated >= 0 )
    {
      if ( *((_DWORD *)this + 27) )
      {
        if ( v24 )
        {
          if ( a2 )
            *a2 = 1;
          if ( a3 )
            *a3 = 1;
        }
      }
      else if ( a2 )
      {
        *a2 = 1;
      }
      *((_DWORD *)this + 27) = 1;
      goto LABEL_26;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
      return v14;
    if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_33;
    v16 = 17;
LABEL_23:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, (unsigned int)updated);
    goto LABEL_32;
  }
  v14 = 0;
  if ( LocationHeaderAddressFamily != 2 )
    goto LABEL_26;
  updated = UpdateNetworkLocationEntry((struct _SSDP_REQUEST *)v7, 1u, (struct _NETWORK_LOCATION_ENTRY *)v11, &v24);
  v14 = updated;
  if ( updated < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
      return v14;
    if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_33;
    v16 = 18;
    goto LABEL_23;
  }
  if ( *((_DWORD *)this + 28) )
  {
    if ( v24 )
    {
      if ( a2 )
        *a2 = 1;
      if ( a3 )
        *a3 = 1;
    }
  }
  else if ( a2 )
  {
    *a2 = 1;
  }
  *((_DWORD *)this + 28) = 1;
LABEL_26:
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
      *(_QWORD *)(*((_QWORD *)this + 11) + 48LL));
    v15 = WPP_GLOBAL_Control;
  }
  if ( v14 )
    goto LABEL_33;
  return v14;
}

```

## disassembly

```asm
0x180008610  push    rbx
0x180008612  push    rbp
0x180008613  push    rsi
0x180008614  push    rdi
0x180008615  push    r14
0x180008617  push    r15
0x180008619  sub     rsp, 38h
0x18000861d  mov     rax, [rcx+58h]
0x180008621  mov     r15, r8
0x180008624  mov     r14, rdx
0x180008627  mov     [rsp+68h+arg_0], 0
0x18000862f  mov     rdi, rcx
0x180008632  cmp     qword ptr [rax+30h], 0
0x180008637  jz      loc_1800087A6
0x18000863d  cmp     qword ptr [rax], 0
0x180008641  jz      loc_1800087A6
0x180008647  lea     rsi, [rcx+8]
0x18000864b  test    rsi, rsi
0x18000864e  jz      loc_1800087F1
0x180008654  mov     rcx, [rsi+50h]
0x180008658  mov     rcx, [rcx+30h]; AddressString
0x18000865c  call    ?GetLocationHeaderAddressFamily@@YAKPEAD@Z; GetLocationHeaderAddressFamily(char *)
0x180008661  mov     ebp, eax
0x180008663  test    eax, eax
0x180008665  jz      loc_1800087DE
0x18000866b  movups  xmm0, xmmword ptr [rdi+28h]
0x18000866f  mov     r9d, [rdi+68h]
0x180008673  xor     edx, edx
0x180008675  movaps  [rsp+68h+var_48], xmm0
0x18000867a  mov     r10, qword ptr [rsp+68h+var_48+8]
0x18000867f  mov     r11, qword ptr [rsp+68h+var_48]
0x180008684  cmp     edx, r9d
0x180008687  jnb     loc_1800087F8
0x18000868d  mov     r8d, edx
0x180008690  shl     r8, 6
0x180008694  add     r8, [rdi+60h]; struct _NETWORK_LOCATION_ENTRY *
0x180008698  mov     rax, [r8+30h]
0x18000869c  sub     rax, r11
0x18000869f  jnz     short loc_1800086A8
0x1800086a1  mov     rax, [r8+38h]
0x1800086a5  sub     rax, r10
0x1800086a8  test    rax, rax
0x1800086ab  jz      short loc_1800086B1
0x1800086ad  inc     edx
0x1800086af  jmp     short loc_180008684
0x1800086b1  test    r8, r8
0x1800086b4  jz      loc_1800087F8
0x1800086ba  cmp     ebp, 1
0x1800086bd  jnz     short loc_1800086E8
0x1800086bf  lea     r9, [rsp+68h+arg_0]; int *
0x1800086c4  xor     edx, edx; unsigned int
0x1800086c6  mov     rcx, rsi; struct _SSDP_REQUEST *
0x1800086c9  call    ?UpdateNetworkLocationEntry@@YAJPEAU_SSDP_REQUEST@@KPEAU_NETWORK_LOCATION_ENTRY@@PEAH@Z; UpdateNetworkLocationEntry(_SSDP_REQUEST *,ulong,_NETWORK_LOCATION_ENTRY *,int *)
0x1800086ce  mov     ebx, eax
0x1800086d0  test    eax, eax
0x1800086d2  js      loc_18000889A
0x1800086d8  cmp     dword ptr [rdi+6Ch], 0
0x1800086dc  jnz     short loc_180008742
0x1800086de  test    r14, r14
0x1800086e1  jz      short loc_18000874D
0x1800086e3  mov     [r14], ebp
0x1800086e6  jmp     short loc_18000874D
0x1800086e8  xor     ebx, ebx
0x1800086ea  cmp     ebp, 2
0x1800086ed  jnz     short loc_180008754
0x1800086ef  lea     r9, [rsp+68h+arg_0]; int *
0x1800086f4  mov     edx, 1; unsigned int
0x1800086f9  mov     rcx, rsi; struct _SSDP_REQUEST *
0x1800086fc  call    ?UpdateNetworkLocationEntry@@YAJPEAU_SSDP_REQUEST@@KPEAU_NETWORK_LOCATION_ENTRY@@PEAH@Z; UpdateNetworkLocationEntry(_SSDP_REQUEST *,ulong,_NETWORK_LOCATION_ENTRY *,int *)
0x180008701  mov     ebx, eax
0x180008703  test    eax, eax
0x180008705  jns     loc_1800088E6
0x18000870b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008712  lea     rsi, WPP_GLOBAL_Control
0x180008719  cmp     rcx, rsi
0x18000871c  jz      short loc_18000876B
0x18000871e  test    byte ptr [rcx+1Ch], 1
0x180008722  jz      loc_1800087B9
0x180008728  mov     edx, 12h
0x18000872d  mov     rcx, [rcx+10h]
0x180008731  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180008738  mov     r9d, eax
0x18000873b  call    WPP_SF_d
0x180008740  jmp     short loc_1800087B2
0x180008742  cmp     [rsp+68h+arg_0], 0
0x180008747  jnz     loc_1800088C5
0x18000874d  mov     dword ptr [rdi+6Ch], 1
0x180008754  mov     rcx, cs:WPP_GLOBAL_Control
0x18000875b  lea     rsi, WPP_GLOBAL_Control
0x180008762  cmp     rcx, rsi
0x180008765  jnz     short loc_18000877A
0x180008767  test    ebx, ebx
0x180008769  jnz     short loc_1800087B9
0x18000876b  mov     eax, ebx
0x18000876d  add     rsp, 38h
0x180008771  pop     r15
0x180008773  pop     r14
0x180008775  pop     rdi
0x180008776  pop     rsi
0x180008777  pop     rbp
0x180008778  pop     rbx
0x180008779  retn
0x18000877a  test    byte ptr [rcx+1Ch], 8
0x18000877e  jz      short loc_180008767
0x180008780  mov     r9, [rdi+58h]
0x180008784  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000878b  mov     rcx, [rcx+10h]
0x18000878f  mov     edx, 13h
0x180008794  mov     r9, [r9+30h]
0x180008798  call    WPP_SF_s
0x18000879d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087a4  jmp     short loc_180008767
0x1800087a6  mov     ebx, 80070057h
0x1800087ab  lea     rsi, WPP_GLOBAL_Control
0x1800087b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087b9  cmp     rcx, rsi
0x1800087bc  jz      short loc_18000876B
0x1800087be  test    byte ptr [rcx+1Ch], 1
0x1800087c2  jz      short loc_18000876B
0x1800087c4  mov     rcx, [rcx+10h]
0x1800087c8  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x1800087cf  mov     edx, 14h
0x1800087d4  mov     r9d, ebx
0x1800087d7  call    WPP_SF_d
0x1800087dc  jmp     short loc_18000876B
0x1800087de  mov     rcx, [rsi+50h]
0x1800087e2  mov     rcx, [rcx]; char *
0x1800087e5  call    ?GetHostHeaderAddressFamily@@YAKPEAD@Z; GetHostHeaderAddressFamily(char *)
0x1800087ea  mov     ebp, eax
0x1800087ec  jmp     loc_18000866B
0x1800087f1  xor     ebp, ebp
0x1800087f3  jmp     loc_18000866B
0x1800087f8  mov     rcx, [rdi+60h]
0x1800087fc  test    rcx, rcx
0x1800087ff  jnz     short loc_180008839
0x180008801  mov     ecx, 40h ; '@'; Size
0x180008806  call    cs:__imp_malloc
0x18000880c  mov     [rdi+60h], rax
0x180008810  test    rax, rax
0x180008813  jnz     short loc_18000881C
0x180008815  mov     ebx, 8007000Eh
0x18000881a  jmp     short loc_1800087AB
0x18000881c  xor     edx, edx; Val
0x18000881e  mov     dword ptr [rdi+68h], 1
0x180008825  mov     r8d, 40h ; '@'; Size
0x18000882b  mov     rcx, rax; void *
0x18000882e  call    memset_0
0x180008833  mov     r8, [rdi+60h]
0x180008837  jmp     short loc_180008884
0x180008839  lea     edx, [r9+1]
0x18000883d  shl     rdx, 6
0x180008841  call    cs:__imp__o_realloc
0x180008847  test    rax, rax
0x18000884a  jnz     short loc_180008856
0x18000884c  mov     ebx, 8007000Eh
0x180008851  jmp     loc_1800087AB
0x180008856  mov     ecx, [rdi+68h]
0x180008859  xor     edx, edx; Val
0x18000885b  shl     rcx, 6
0x18000885f  mov     r8d, 40h ; '@'; Size
0x180008865  add     rcx, rax; void *
0x180008868  mov     [rdi+60h], rax
0x18000886c  call    memset_0
0x180008871  mov     eax, [rdi+68h]
0x180008874  mov     r8d, eax
0x180008877  shl     r8, 6
0x18000887b  add     r8, [rdi+60h]
0x18000887f  inc     eax
0x180008881  mov     [rdi+68h], eax
0x180008884  movups  xmm0, xmmword ptr [rdi+28h]
0x180008888  mov     [rsp+68h+arg_0], 1
0x180008890  movups  xmmword ptr [r8+30h], xmm0
0x180008895  jmp     loc_1800086BA
0x18000889a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088a1  lea     rsi, WPP_GLOBAL_Control
0x1800088a8  cmp     rcx, rsi
0x1800088ab  jz      loc_18000876B
0x1800088b1  test    byte ptr [rcx+1Ch], 1
0x1800088b5  jz      loc_1800087B9
0x1800088bb  mov     edx, 11h
0x1800088c0  jmp     loc_18000872D
0x1800088c5  test    r14, r14
0x1800088c8  jz      short loc_1800088D1
0x1800088ca  mov     dword ptr [r14], 1
0x1800088d1  test    r15, r15
0x1800088d4  jz      loc_18000874D
0x1800088da  mov     dword ptr [r15], 1
0x1800088e1  jmp     loc_18000874D
0x1800088e6  cmp     dword ptr [rdi+70h], 0
0x1800088ea  jz      short loc_18000890D
0x1800088ec  cmp     [rsp+68h+arg_0], 0
0x1800088f1  jz      short loc_180008919
0x1800088f3  test    r14, r14
0x1800088f6  jz      short loc_1800088FF
0x1800088f8  mov     dword ptr [r14], 1
0x1800088ff  test    r15, r15
0x180008902  jz      short loc_180008919
0x180008904  mov     dword ptr [r15], 1
0x18000890b  jmp     short loc_180008919
0x18000890d  test    r14, r14
0x180008910  jz      short loc_180008919
0x180008912  mov     dword ptr [r14], 1
0x180008919  mov     dword ptr [rdi+70h], 1
0x180008920  jmp     loc_180008754
```
