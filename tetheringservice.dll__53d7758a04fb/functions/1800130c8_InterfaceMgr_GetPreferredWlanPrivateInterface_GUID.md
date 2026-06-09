# InterfaceMgr::GetPreferredWlanPrivateInterface(_GUID *)

- ea: `0x1800130c8`
- end: `0x1800132c0`
- name: `?GetPreferredWlanPrivateInterface@InterfaceMgr@@CAJPEAU_GUID@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012a90`

## callees

- `0x180002590`
- `0x18000bf4c`
- `0x18000bf74`
- `0x1800130c8`
- `0x1800140f4`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x1800131f0`
- `wlanapi!WlanFreeMemory` at `0x18001328d`
- `wlanapi!WlanFreeMemory` at `0x1800131f0`
- `wlanapi!WlanFreeMemory` at `0x18001328d`
- `wlanapi!WlanCloseHandle` at `0x18001329f`
- `wlanapi!WlanCloseHandle` at `0x18001329f`
- `wlanapi!WlanEnumInterfaces` at `0x1800131c2`
- `wlanapi!WlanEnumInterfaces` at `0x1800131c2`
- `wlanapi!WlanOpenHandle` at `0x180013154`
- `wlanapi!WlanOpenHandle` at `0x180013154`

## pseudocode

```c
__int64 __fastcall InterfaceMgr::GetPreferredWlanPrivateInterface(struct _GUID *a1)
{
  signed int v2; // eax
  int v3; // r8d
  signed int v4; // ebx
  TetheringServiceTelemetry *v5; // rcx
  __int64 v6; // rdx
  signed int v7; // eax
  PVOID v8; // rcx
  PVOID v9; // rcx
  PVOID pMemory; // [rsp+30h] [rbp-19h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+38h] [rbp-11h] BYREF
  void *phClientHandle; // [rsp+40h] [rbp-9h] BYREF
  PVOID *p_pMemory; // [rsp+48h] [rbp-1h]
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+50h] [rbp+7h] BYREF
  char v16; // [rsp+58h] [rbp+Fh]
  GUID v17; // [rsp+60h] [rbp+17h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
  pMemory = 0;
  pdwNegotiatedVersion = 0;
  *a1 = GUID_NULL;
  phClientHandle = (void *)-1LL;
  v17 = GUID_NULL;
  v2 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  v4 = v2;
  if ( v2 > 0 )
    v4 = (unsigned __int16)v2 | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    v6 = 133;
    goto LABEL_10;
  }
  p_pMemory = &pMemory;
  ppInterfaceList = 0;
  v16 = 1;
  v7 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList);
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x80070000;
  if ( v16 )
  {
    v8 = *p_pMemory;
    *p_pMemory = ppInterfaceList;
    if ( v8 )
      WlanFreeMemory(v8);
  }
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    v6 = 134;
    goto LABEL_10;
  }
  if ( *(_DWORD *)pMemory )
  {
    v17 = *(GUID *)((char *)pMemory + 8);
    *a1 = v17;
    goto LABEL_25;
  }
  v4 = -2147023728;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_29;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 135;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, (unsigned int)v4);
LABEL_25:
    v5 = WPP_GLOBAL_Control;
  }
LABEL_26:
  if ( v5 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_d_guid_(*((_QWORD *)v5 + 2), 136, v3, v4, (__int64)&v17);
LABEL_29:
  v9 = pMemory;
  pMemory = 0;
  if ( v9 )
    WlanFreeMemory(v9);
  if ( phClientHandle != (void *)-1LL )
    WlanCloseHandle(phClientHandle, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800130c8  push    rbp
0x1800130ca  push    rbx
0x1800130cb  push    rdi
0x1800130cc  push    r14
0x1800130ce  lea     rbp, [rsp-3Fh]
0x1800130d3  sub     rsp, 88h
0x1800130da  mov     rax, cs:__security_cookie
0x1800130e1  xor     rax, rsp
0x1800130e4  mov     [rbp+57h+var_30], rax
0x1800130e8  mov     rdi, rcx
0x1800130eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130f2  lea     r14, WPP_GLOBAL_Control
0x1800130f9  cmp     rcx, r14
0x1800130fc  jz      short loc_180013119
0x1800130fe  test    byte ptr [rcx+1Ch], 8
0x180013102  jz      short loc_180013119
0x180013104  mov     rcx, [rcx+10h]
0x180013108  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x18001310f  mov     edx, 84h
0x180013114  call    WPP_SF_
0x180013119  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180013120  xor     edx, edx; pReserved
0x180013122  mov     [rbp+57h+pMemory], 0
0x18001312a  lea     r9, [rbp+57h+phClientHandle]; phClientHandle
0x18001312e  mov     [rbp+57h+pdwNegotiatedVersion], 0
0x180013135  movdqu  xmmword ptr [rdi], xmm0
0x180013139  lea     r8, [rbp+57h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18001313d  mov     [rbp+57h+phClientHandle], 0FFFFFFFFFFFFFFFFh
0x180013145  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18001314c  lea     ecx, [rdx+2]; dwClientVersion
0x18001314f  movdqu  [rbp+57h+var_40], xmm1
0x180013154  call    cs:__imp_WlanOpenHandle
0x18001315a  mov     ebx, eax
0x18001315c  test    eax, eax
0x18001315e  jle     short loc_180013169
0x180013160  movzx   ebx, ax
0x180013163  or      ebx, 80070000h
0x180013169  test    ebx, ebx
0x18001316b  jns     short loc_1800131A4
0x18001316d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013174  cmp     rcx, r14
0x180013177  jz      loc_18001327C
0x18001317d  test    byte ptr [rcx+1Ch], 1
0x180013181  jz      loc_180013257
0x180013187  mov     edx, 85h
0x18001318c  mov     rcx, [rcx+10h]
0x180013190  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180013197  mov     r9d, ebx
0x18001319a  call    WPP_SF_d
0x18001319f  jmp     loc_180013250
0x1800131a4  mov     rcx, [rbp+57h+phClientHandle]; hClientHandle
0x1800131a8  lea     rax, [rbp+57h+pMemory]
0x1800131ac  lea     r8, [rbp+57h+ppInterfaceList]; ppInterfaceList
0x1800131b0  mov     [rbp+57h+var_58], rax
0x1800131b4  xor     edx, edx; pReserved
0x1800131b6  mov     [rbp+57h+ppInterfaceList], 0
0x1800131be  mov     [rbp+57h+var_48], 1
0x1800131c2  call    cs:__imp_WlanEnumInterfaces
0x1800131c8  mov     ebx, eax
0x1800131ca  test    eax, eax
0x1800131cc  jle     short loc_1800131D7
0x1800131ce  movzx   ebx, ax
0x1800131d1  or      ebx, 80070000h
0x1800131d7  cmp     [rbp+57h+var_48], 0
0x1800131db  jz      short loc_1800131F6
0x1800131dd  mov     rdx, [rbp+57h+var_58]
0x1800131e1  mov     rax, [rbp+57h+ppInterfaceList]
0x1800131e5  mov     rcx, [rdx]; pMemory
0x1800131e8  mov     [rdx], rax
0x1800131eb  test    rcx, rcx
0x1800131ee  jz      short loc_1800131F6
0x1800131f0  call    cs:__imp_WlanFreeMemory
0x1800131f6  test    ebx, ebx
0x1800131f8  jns     short loc_180013216
0x1800131fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180013201  cmp     rcx, r14
0x180013204  jz      short loc_18001327C
0x180013206  test    byte ptr [rcx+1Ch], 1
0x18001320a  jz      short loc_180013257
0x18001320c  mov     edx, 86h
0x180013211  jmp     loc_18001318C
0x180013216  mov     rax, [rbp+57h+pMemory]
0x18001321a  cmp     dword ptr [rax], 1
0x18001321d  jnb     short loc_180013240
0x18001321f  mov     ebx, 80070490h
0x180013224  mov     rcx, cs:WPP_GLOBAL_Control
0x18001322b  cmp     rcx, r14
0x18001322e  jz      short loc_18001327C
0x180013230  test    byte ptr [rcx+1Ch], 1
0x180013234  jz      short loc_180013257
0x180013236  mov     edx, 87h
0x18001323b  jmp     loc_18001318C
0x180013240  mov     rax, [rbp+57h+pMemory]
0x180013244  movups  xmm0, xmmword ptr [rax+8]
0x180013248  movups  [rbp+57h+var_40], xmm0
0x18001324c  movdqu  xmmword ptr [rdi], xmm0
0x180013250  mov     rcx, cs:WPP_GLOBAL_Control
0x180013257  cmp     rcx, r14
0x18001325a  jz      short loc_18001327C
0x18001325c  test    byte ptr [rcx+1Ch], 8
0x180013260  jz      short loc_18001327C
0x180013262  mov     rcx, [rcx+10h]
0x180013266  lea     rax, [rbp+57h+var_40]
0x18001326a  mov     edx, 88h
0x18001326f  mov     [rsp+0A0h+var_80], rax
0x180013274  mov     r9d, ebx
0x180013277  call    WPP_SF_d_guid_
0x18001327c  mov     rcx, [rbp+57h+pMemory]; pMemory
0x180013280  mov     [rbp+57h+pMemory], 0
0x180013288  test    rcx, rcx
0x18001328b  jz      short loc_180013293
0x18001328d  call    cs:__imp_WlanFreeMemory
0x180013293  mov     rcx, [rbp+57h+phClientHandle]; hClientHandle
0x180013297  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001329b  jz      short loc_1800132A5
0x18001329d  xor     edx, edx; pReserved
0x18001329f  call    cs:__imp_WlanCloseHandle
0x1800132a5  mov     eax, ebx
0x1800132a7  mov     rcx, [rbp+57h+var_30]
0x1800132ab  xor     rcx, rsp; StackCookie
0x1800132ae  call    __security_check_cookie
0x1800132b3  add     rsp, 88h
0x1800132ba  pop     r14
0x1800132bc  pop     rdi
0x1800132bd  pop     rbx
0x1800132be  pop     rbp
0x1800132bf  retn
```
