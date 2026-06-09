# CSsdpCacheEntry::HrGetRequest(ulong,_GUID,_SSDP_REQUEST *)

- ea: `0x180009a84`
- end: `0x180009b71`
- name: `?HrGetRequest@CSsdpCacheEntry@@QEAAJKU_GUID@@PEAU_SSDP_REQUEST@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, unsigned int, struct _GUID *__struct_ptr, struct _SSDP_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016e2c`

## callees

- `0x180008190`
- `0x180008304`
- `0x180009a84`
- `0x18000b28c`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009b55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009b55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009aa6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009aa6`

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
0x180009a84  push    rbx
0x180009a86  push    rbp
0x180009a87  push    rsi
0x180009a88  push    rdi
0x180009a89  push    r14
0x180009a8b  push    r15
0x180009a8d  sub     rsp, 38h
0x180009a91  lea     r15, [rcx+0D8h]
0x180009a98  mov     rdi, rcx
0x180009a9b  mov     rcx, r15; lpCriticalSection
0x180009a9e  mov     rsi, r9
0x180009aa1  mov     r14, r8
0x180009aa4  mov     ebp, edx
0x180009aa6  call    cs:__imp_EnterCriticalSection
0x180009aad  nop     dword ptr [rax+rax+00h]
0x180009ab2  lea     rdx, [rdi+8]; struct _SSDP_REQUEST *
0x180009ab6  mov     rcx, rsi; struct _SSDP_REQUEST *
0x180009ab9  call    ?CopySsdpRequest@@YAHPEAU_SSDP_REQUEST@@PEBU1@@Z; CopySsdpRequest(_SSDP_REQUEST *,_SSDP_REQUEST const *)
0x180009abe  test    eax, eax
0x180009ac0  jnz     short loc_180009AC9
0x180009ac2  mov     ebx, 8007000Eh
0x180009ac7  jmp     short loc_180009B19
0x180009ac9  cmp     ebp, 1
0x180009acc  jnz     short loc_180009AE0
0x180009ace  cmp     dword ptr [rdi+6Ch], 0
0x180009ad2  jz      short loc_180009AD9
0x180009ad4  xor     r9d, r9d
0x180009ad7  jmp     short loc_180009AF0
0x180009ad9  mov     ebx, 80004005h
0x180009ade  jmp     short loc_180009B0C
0x180009ae0  xor     ebx, ebx
0x180009ae2  cmp     ebp, 2
0x180009ae5  jnz     short loc_180009B52
0x180009ae7  cmp     [rdi+70h], ebx
0x180009aea  jz      short loc_180009B14
0x180009aec  lea     r9d, [rbx+1]; unsigned int
0x180009af0  movaps  xmm0, xmmword ptr [r14]
0x180009af4  lea     r8, [rsp+68h+var_48]; struct _GUID
0x180009af9  mov     rdx, rsi; struct _SSDP_REQUEST *
0x180009afc  movdqa  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x180009b02  mov     rcx, rdi; this
0x180009b05  call    ?ComposeSsdpRequestFromNetworkLocation@CSsdpCacheEntry@@AEAAJPEAU_SSDP_REQUEST@@U_GUID@@K@Z; CSsdpCacheEntry::ComposeSsdpRequestFromNetworkLocation(_SSDP_REQUEST *,_GUID,ulong)
0x180009b0a  mov     ebx, eax
0x180009b0c  test    ebx, ebx
0x180009b0e  js      short loc_180009B19
0x180009b10  jnz     short loc_180009B21
0x180009b12  jmp     short loc_180009B52
0x180009b14  mov     ebx, 80004005h
0x180009b19  mov     rcx, rsi; struct _SSDP_REQUEST *
0x180009b1c  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180009b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b28  lea     rax, WPP_GLOBAL_Control
0x180009b2f  cmp     rcx, rax
0x180009b32  jz      short loc_180009B52
0x180009b34  test    byte ptr [rcx+1Ch], 1
0x180009b38  jz      short loc_180009B52
0x180009b3a  mov     rcx, [rcx+10h]
0x180009b3e  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180009b45  mov     edx, 36h ; '6'
0x180009b4a  mov     r9d, ebx
0x180009b4d  call    WPP_SF_d
0x180009b52  mov     rcx, r15; lpCriticalSection
0x180009b55  call    cs:__imp_LeaveCriticalSection
0x180009b5c  nop     dword ptr [rax+rax+00h]
0x180009b61  mov     eax, ebx
0x180009b63  add     rsp, 38h
0x180009b67  pop     r15
0x180009b69  pop     r14
0x180009b6b  pop     rdi
0x180009b6c  pop     rsi
0x180009b6d  pop     rbp
0x180009b6e  pop     rbx
0x180009b6f  retn
```
