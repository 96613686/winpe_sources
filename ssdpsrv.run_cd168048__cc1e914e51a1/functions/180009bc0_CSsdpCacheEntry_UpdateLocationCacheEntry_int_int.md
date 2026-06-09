# CSsdpCacheEntry::UpdateLocationCacheEntry(int *,int *)

- ea: `0x180009bc0`
- end: `0x180009ee2`
- name: `?UpdateLocationCacheEntry@CSsdpCacheEntry@@AEAAJPEAH0@Z`
- size: `802`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, int *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180006a60`
- `0x18000baf8`

## callees

- `0x180009bc0`
- `0x18000a3f0`
- `0x18000a538`
- `0x1800271fc`
- `0x180027e50`
- `0x18002911c`
- `0x18002fe28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009db7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009db7`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180009df8`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180009df8`

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
0x180009bc0  push    rbx
0x180009bc2  push    rbp
0x180009bc3  push    rsi
0x180009bc4  push    rdi
0x180009bc5  push    r14
0x180009bc7  push    r15
0x180009bc9  sub     rsp, 38h
0x180009bcd  mov     rax, [rcx+58h]
0x180009bd1  mov     r15, r8
0x180009bd4  mov     r14, rdx
0x180009bd7  mov     [rsp+68h+arg_0], 0
0x180009bdf  mov     rdi, rcx
0x180009be2  cmp     qword ptr [rax+30h], 0
0x180009be7  jz      loc_180009D57
0x180009bed  cmp     qword ptr [rax], 0
0x180009bf1  jz      loc_180009D57
0x180009bf7  lea     rsi, [rcx+8]
0x180009bfb  test    rsi, rsi
0x180009bfe  jz      loc_180009DA2
0x180009c04  mov     rcx, [rsi+50h]
0x180009c08  mov     rcx, [rcx+30h]; AddressString
0x180009c0c  call    ?GetLocationHeaderAddressFamily@@YAKPEAD@Z; GetLocationHeaderAddressFamily(char *)
0x180009c11  mov     ebp, eax
0x180009c13  test    eax, eax
0x180009c15  jz      loc_180009D8F
0x180009c1b  movups  xmm0, xmmword ptr [rdi+28h]
0x180009c1f  mov     r9d, [rdi+68h]
0x180009c23  xor     edx, edx
0x180009c25  movaps  [rsp+68h+var_48], xmm0
0x180009c2a  mov     r10, qword ptr [rsp+68h+var_48+8]
0x180009c2f  mov     r11, qword ptr [rsp+68h+var_48]
0x180009c34  cmp     edx, r9d
0x180009c37  jnb     loc_180009DA9
0x180009c3d  mov     r8d, edx
0x180009c40  shl     r8, 6
0x180009c44  add     r8, [rdi+60h]; struct _NETWORK_LOCATION_ENTRY *
0x180009c48  mov     rax, [r8+30h]
0x180009c4c  sub     rax, r11
0x180009c4f  jnz     short loc_180009C58
0x180009c51  mov     rax, [r8+38h]
0x180009c55  sub     rax, r10
0x180009c58  test    rax, rax
0x180009c5b  jz      short loc_180009C61
0x180009c5d  inc     edx
0x180009c5f  jmp     short loc_180009C34
0x180009c61  test    r8, r8
0x180009c64  jz      loc_180009DA9
0x180009c6a  cmp     ebp, 1
0x180009c6d  jnz     short loc_180009C98
0x180009c6f  lea     r9, [rsp+68h+arg_0]; int *
0x180009c74  xor     edx, edx; unsigned int
0x180009c76  mov     rcx, rsi; struct _SSDP_REQUEST *
0x180009c79  call    ?UpdateNetworkLocationEntry@@YAJPEAU_SSDP_REQUEST@@KPEAU_NETWORK_LOCATION_ENTRY@@PEAH@Z; UpdateNetworkLocationEntry(_SSDP_REQUEST *,ulong,_NETWORK_LOCATION_ENTRY *,int *)
0x180009c7e  mov     ebx, eax
0x180009c80  test    eax, eax
0x180009c82  js      loc_180009E57
0x180009c88  cmp     dword ptr [rdi+6Ch], 0
0x180009c8c  jnz     short loc_180009CF2
0x180009c8e  test    r14, r14
0x180009c91  jz      short loc_180009CFD
0x180009c93  mov     [r14], ebp
0x180009c96  jmp     short loc_180009CFD
0x180009c98  xor     ebx, ebx
0x180009c9a  cmp     ebp, 2
0x180009c9d  jnz     short loc_180009D04
0x180009c9f  lea     r9, [rsp+68h+arg_0]; int *
0x180009ca4  mov     edx, 1; unsigned int
0x180009ca9  mov     rcx, rsi; struct _SSDP_REQUEST *
0x180009cac  call    ?UpdateNetworkLocationEntry@@YAJPEAU_SSDP_REQUEST@@KPEAU_NETWORK_LOCATION_ENTRY@@PEAH@Z; UpdateNetworkLocationEntry(_SSDP_REQUEST *,ulong,_NETWORK_LOCATION_ENTRY *,int *)
0x180009cb1  mov     ebx, eax
0x180009cb3  test    eax, eax
0x180009cb5  jns     loc_180009EA3
0x180009cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cc2  lea     rsi, WPP_GLOBAL_Control
0x180009cc9  cmp     rcx, rsi
0x180009ccc  jz      short loc_180009D1B
0x180009cce  test    byte ptr [rcx+1Ch], 1
0x180009cd2  jz      loc_180009D6A
0x180009cd8  mov     edx, 12h
0x180009cdd  mov     rcx, [rcx+10h]
0x180009ce1  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180009ce8  mov     r9d, eax
0x180009ceb  call    WPP_SF_d
0x180009cf0  jmp     short loc_180009D63
0x180009cf2  cmp     [rsp+68h+arg_0], 0
0x180009cf7  jnz     loc_180009E82
0x180009cfd  mov     dword ptr [rdi+6Ch], 1
0x180009d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d0b  lea     rsi, WPP_GLOBAL_Control
0x180009d12  cmp     rcx, rsi
0x180009d15  jnz     short loc_180009D2B
0x180009d17  test    ebx, ebx
0x180009d19  jnz     short loc_180009D6A
0x180009d1b  mov     eax, ebx
0x180009d1d  add     rsp, 38h
0x180009d21  pop     r15
0x180009d23  pop     r14
0x180009d25  pop     rdi
0x180009d26  pop     rsi
0x180009d27  pop     rbp
0x180009d28  pop     rbx
0x180009d29  retn
0x180009d2b  test    byte ptr [rcx+1Ch], 8
0x180009d2f  jz      short loc_180009D17
0x180009d31  mov     r9, [rdi+58h]
0x180009d35  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180009d3c  mov     rcx, [rcx+10h]
0x180009d40  mov     edx, 13h
0x180009d45  mov     r9, [r9+30h]
0x180009d49  call    WPP_SF_s
0x180009d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d55  jmp     short loc_180009D17
0x180009d57  mov     ebx, 80070057h
0x180009d5c  lea     rsi, WPP_GLOBAL_Control
0x180009d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d6a  cmp     rcx, rsi
0x180009d6d  jz      short loc_180009D1B
0x180009d6f  test    byte ptr [rcx+1Ch], 1
0x180009d73  jz      short loc_180009D1B
0x180009d75  mov     rcx, [rcx+10h]
0x180009d79  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180009d80  mov     edx, 14h
0x180009d85  mov     r9d, ebx
0x180009d88  call    WPP_SF_d
0x180009d8d  jmp     short loc_180009D1B
0x180009d8f  mov     rcx, [rsi+50h]
0x180009d93  mov     rcx, [rcx]; char *
0x180009d96  call    ?GetHostHeaderAddressFamily@@YAKPEAD@Z; GetHostHeaderAddressFamily(char *)
0x180009d9b  mov     ebp, eax
0x180009d9d  jmp     loc_180009C1B
0x180009da2  xor     ebp, ebp
0x180009da4  jmp     loc_180009C1B
0x180009da9  mov     rcx, [rdi+60h]
0x180009dad  test    rcx, rcx
0x180009db0  jnz     short loc_180009DF0
0x180009db2  mov     ecx, 40h ; '@'; Size
0x180009db7  call    cs:__imp_malloc
0x180009dbe  nop     dword ptr [rax+rax+00h]
0x180009dc3  mov     [rdi+60h], rax
0x180009dc7  test    rax, rax
0x180009dca  jnz     short loc_180009DD3
0x180009dcc  mov     ebx, 8007000Eh
0x180009dd1  jmp     short loc_180009D5C
0x180009dd3  xor     edx, edx; Val
0x180009dd5  mov     dword ptr [rdi+68h], 1
0x180009ddc  mov     r8d, 40h ; '@'; Size
0x180009de2  mov     rcx, rax; void *
0x180009de5  call    memset_0
0x180009dea  mov     r8, [rdi+60h]
0x180009dee  jmp     short loc_180009E41
0x180009df0  lea     edx, [r9+1]
0x180009df4  shl     rdx, 6
0x180009df8  call    cs:__imp__o_realloc
0x180009dff  nop     dword ptr [rax+rax+00h]
0x180009e04  test    rax, rax
0x180009e07  jnz     short loc_180009E13
0x180009e09  mov     ebx, 8007000Eh
0x180009e0e  jmp     loc_180009D5C
0x180009e13  mov     ecx, [rdi+68h]
0x180009e16  xor     edx, edx; Val
0x180009e18  shl     rcx, 6
0x180009e1c  mov     r8d, 40h ; '@'; Size
0x180009e22  add     rcx, rax; void *
0x180009e25  mov     [rdi+60h], rax
0x180009e29  call    memset_0
0x180009e2e  mov     eax, [rdi+68h]
0x180009e31  mov     r8d, eax
0x180009e34  shl     r8, 6
0x180009e38  add     r8, [rdi+60h]
0x180009e3c  inc     eax
0x180009e3e  mov     [rdi+68h], eax
0x180009e41  movups  xmm0, xmmword ptr [rdi+28h]
0x180009e45  mov     [rsp+68h+arg_0], 1
0x180009e4d  movups  xmmword ptr [r8+30h], xmm0
0x180009e52  jmp     loc_180009C6A
0x180009e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e5e  lea     rsi, WPP_GLOBAL_Control
0x180009e65  cmp     rcx, rsi
0x180009e68  jz      loc_180009D1B
0x180009e6e  test    byte ptr [rcx+1Ch], 1
0x180009e72  jz      loc_180009D6A
0x180009e78  mov     edx, 11h
0x180009e7d  jmp     loc_180009CDD
0x180009e82  test    r14, r14
0x180009e85  jz      short loc_180009E8E
0x180009e87  mov     dword ptr [r14], 1
0x180009e8e  test    r15, r15
0x180009e91  jz      loc_180009CFD
0x180009e97  mov     dword ptr [r15], 1
0x180009e9e  jmp     loc_180009CFD
0x180009ea3  cmp     dword ptr [rdi+70h], 0
0x180009ea7  jz      short loc_180009ECA
0x180009ea9  cmp     [rsp+68h+arg_0], 0
0x180009eae  jz      short loc_180009ED6
0x180009eb0  test    r14, r14
0x180009eb3  jz      short loc_180009EBC
0x180009eb5  mov     dword ptr [r14], 1
0x180009ebc  test    r15, r15
0x180009ebf  jz      short loc_180009ED6
0x180009ec1  mov     dword ptr [r15], 1
0x180009ec8  jmp     short loc_180009ED6
0x180009eca  test    r14, r14
0x180009ecd  jz      short loc_180009ED6
0x180009ecf  mov     dword ptr [r14], 1
0x180009ed6  mov     dword ptr [rdi+70h], 1
0x180009edd  jmp     loc_180009D04
```
