# CSsdpCacheEntry::HrGetRequest(ulong,_GUID,_SSDP_REQUEST *)

- ea: `0x1800084e0`
- end: `0x1800085c0`
- name: `?HrGetRequest@CSsdpCacheEntry@@QEAAJKU_GUID@@PEAU_SSDP_REQUEST@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *this, int, struct _GUID *, struct _NETWORK_LOCATION_INFO **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014868`

## callees

- `0x180006d70`
- `0x180006eb8`
- `0x1800084e0`
- `0x180009cac`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800085ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800085ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008502`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008502`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::HrGetRequest(
        CSsdpCacheEntry *this,
        int a2,
        struct _GUID *a3,
        struct _NETWORK_LOCATION_INFO **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  int v9; // ebx
  unsigned int v10; // r9d
  struct _GUID v12; // [rsp+20h] [rbp-48h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( !(unsigned int)CopySsdpRequest(a4, (CSsdpCacheEntry *)((char *)this + 8)) )
  {
    v9 = -2147024882;
    goto LABEL_15;
  }
  if ( a2 == 1 )
  {
    if ( !*((_DWORD *)this + 27) )
    {
      v9 = -2147467259;
      goto LABEL_11;
    }
    v10 = 0;
  }
  else
  {
    v9 = 0;
    if ( a2 != 2 )
      goto LABEL_19;
    if ( !*((_DWORD *)this + 28) )
    {
      v9 = -2147467259;
      goto LABEL_15;
    }
    v10 = 1;
  }
  v12 = *a3;
  v9 = CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(this, (struct _SSDP_REQUEST *)a4, &v12, v10);
LABEL_11:
  if ( v9 >= 0 )
  {
    if ( !v9 )
      goto LABEL_19;
    goto LABEL_16;
  }
LABEL_15:
  FreeSsdpRequest((struct _SSDP_REQUEST *)a4);
LABEL_16:
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, (unsigned int)v9);
LABEL_19:
  LeaveCriticalSection(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800084e0  push    rbx
0x1800084e2  push    rbp
0x1800084e3  push    rsi
0x1800084e4  push    rdi
0x1800084e5  push    r14
0x1800084e7  push    r15
0x1800084e9  sub     rsp, 38h
0x1800084ed  lea     r15, [rcx+0D8h]
0x1800084f4  mov     rdi, rcx
0x1800084f7  mov     rcx, r15; lpCriticalSection
0x1800084fa  mov     rsi, r9
0x1800084fd  mov     r14, r8
0x180008500  mov     ebp, edx
0x180008502  call    cs:__imp_EnterCriticalSection
0x180008508  lea     rdx, [rdi+8]; struct _SSDP_REQUEST *
0x18000850c  mov     rcx, rsi; struct _SSDP_REQUEST *
0x18000850f  call    ?CopySsdpRequest@@YAHPEAU_SSDP_REQUEST@@PEBU1@@Z; CopySsdpRequest(_SSDP_REQUEST *,_SSDP_REQUEST const *)
0x180008514  test    eax, eax
0x180008516  jnz     short loc_18000851F
0x180008518  mov     ebx, 8007000Eh
0x18000851d  jmp     short loc_18000856F
0x18000851f  cmp     ebp, 1
0x180008522  jnz     short loc_180008536
0x180008524  cmp     dword ptr [rdi+6Ch], 0
0x180008528  jz      short loc_18000852F
0x18000852a  xor     r9d, r9d
0x18000852d  jmp     short loc_180008546
0x18000852f  mov     ebx, 80004005h
0x180008534  jmp     short loc_180008562
0x180008536  xor     ebx, ebx
0x180008538  cmp     ebp, 2
0x18000853b  jnz     short loc_1800085A8
0x18000853d  cmp     [rdi+70h], ebx
0x180008540  jz      short loc_18000856A
0x180008542  lea     r9d, [rbx+1]; unsigned int
0x180008546  movaps  xmm0, xmmword ptr [r14]
0x18000854a  lea     r8, [rsp+68h+var_48]; struct _GUID
0x18000854f  mov     rdx, rsi; struct _SSDP_REQUEST *
0x180008552  movdqa  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x180008558  mov     rcx, rdi; this
0x18000855b  call    ?ComposeSsdpRequestFromNetworkLocation@CSsdpCacheEntry@@AEAAJPEAU_SSDP_REQUEST@@U_GUID@@K@Z; CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(_SSDP_REQUEST *,_GUID,ulong)
0x180008560  mov     ebx, eax
0x180008562  test    ebx, ebx
0x180008564  js      short loc_18000856F
0x180008566  jnz     short loc_180008577
0x180008568  jmp     short loc_1800085A8
0x18000856a  mov     ebx, 80004005h
0x18000856f  mov     rcx, rsi; struct _SSDP_REQUEST *
0x180008572  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180008577  mov     rcx, cs:WPP_GLOBAL_Control
0x18000857e  lea     rax, WPP_GLOBAL_Control
0x180008585  cmp     rcx, rax
0x180008588  jz      short loc_1800085A8
0x18000858a  test    byte ptr [rcx+1Ch], 1
0x18000858e  jz      short loc_1800085A8
0x180008590  mov     rcx, [rcx+10h]
0x180008594  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000859b  mov     edx, 36h ; '6'
0x1800085a0  mov     r9d, ebx
0x1800085a3  call    WPP_SF_d
0x1800085a8  mov     rcx, r15; lpCriticalSection
0x1800085ab  call    cs:__imp_LeaveCriticalSection
0x1800085b1  mov     eax, ebx
0x1800085b3  add     rsp, 38h
0x1800085b7  pop     r15
0x1800085b9  pop     r14
0x1800085bb  pop     rdi
0x1800085bc  pop     rsi
0x1800085bd  pop     rbp
0x1800085be  pop     rbx
0x1800085bf  retn
```
