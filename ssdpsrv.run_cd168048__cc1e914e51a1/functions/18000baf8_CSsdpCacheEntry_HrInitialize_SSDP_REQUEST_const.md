# CSsdpCacheEntry::HrInitialize(_SSDP_REQUEST const *)

- ea: `0x18000baf8`
- end: `0x18000bbe5`
- name: `?HrInitialize@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, const struct _SSDP_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180005260`

## callees

- `0x180008304`
- `0x180009bc0`
- `0x18000baf8`
- `0x18000bbf0`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000bb91`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000bb91`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::HrInitialize(struct _NETWORK_LOCATION_INFO **this, const struct _SSDP_REQUEST *a2)
{
  unsigned int v3; // ebx
  LPCSTR v4; // rcx
  unsigned int updated; // eax
  const char *v6; // rdx
  struct _NETWORK_LOCATION_INFO *v7; // r8
  HashFn *v8; // rcx
  HashFn *v9; // rcx

  if ( !(unsigned int)CopySsdpRequest(this + 1, a2) )
  {
    v3 = -2147467259;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
      return v3;
    if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_12;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, 2147500037LL);
LABEL_11:
    v4 = WPP_GLOBAL_Control;
LABEL_12:
    if ( v4 != (LPCSTR)&WPP_GLOBAL_Control && (v4[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v4 + 2), 29, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v3);
    return v3;
  }
  updated = CSsdpCacheEntry::UpdateLocationCacheEntry((CSsdpCacheEntry *)this, 0, 0);
  v7 = this[11];
  v3 = updated;
  if ( v7 )
  {
    v8 = (HashFn *)*((_QWORD *)v7 + 8);
    if ( v8 )
      *((_DWORD *)this + 64) = HashFn::HashString(v8, v6, (unsigned int)v7);
    v9 = (HashFn *)*((_QWORD *)v7 + 1);
    if ( v9 )
      *((_DWORD *)this + 65) = HashFn::HashString(v9, v6, (unsigned int)v7);
  }
  this[33] = (struct _NETWORK_LOCATION_INFO *)GetTickCount64();
  if ( v3 )
    goto LABEL_11;
  return v3;
}

```

## disassembly

```asm
0x18000baf8  mov     [rsp+arg_0], rbx
0x18000bafd  mov     [rsp+arg_8], rsi
0x18000bb02  push    rdi
0x18000bb03  sub     rsp, 20h
0x18000bb07  mov     rdi, rcx
0x18000bb0a  add     rcx, 8; struct _SSDP_REQUEST *
0x18000bb0e  call    ?CopySsdpRequest@@YAHPEAU_SSDP_REQUEST@@PEBU1@@Z; CopySsdpRequest(_SSDP_REQUEST *,_SSDP_REQUEST const *)
0x18000bb13  lea     rsi, WPP_GLOBAL_Control
0x18000bb1a  test    eax, eax
0x18000bb1c  jnz     short loc_18000BB51
0x18000bb1e  mov     ebx, 80004005h
0x18000bb23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb2a  cmp     rcx, rsi
0x18000bb2d  jz      loc_18000BBD2
0x18000bb33  test    byte ptr [rcx+1Ch], 1
0x18000bb37  jz      short loc_18000BBAF
0x18000bb39  mov     rcx, [rcx+10h]
0x18000bb3d  lea     edx, [rax+1Ch]
0x18000bb40  mov     r9d, ebx
0x18000bb43  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000bb4a  call    WPP_SF_d
0x18000bb4f  jmp     short loc_18000BBA8
0x18000bb51  xor     r8d, r8d; int *
0x18000bb54  xor     edx, edx; int *
0x18000bb56  mov     rcx, rdi; this
0x18000bb59  call    ?UpdateLocationCacheEntry@CSsdpCacheEntry@@AEAAJPEAH0@Z; CSsdpCacheEntry::UpdateLocationCacheEntry(int *,int *)
0x18000bb5e  mov     r8, [rdi+58h]; unsigned int
0x18000bb62  mov     ebx, eax
0x18000bb64  test    r8, r8
0x18000bb67  jz      short loc_18000BB91
0x18000bb69  mov     rcx, [r8+40h]; this
0x18000bb6d  test    rcx, rcx
0x18000bb70  jz      short loc_18000BB7D
0x18000bb72  call    ?HashString@HashFn@@YAKPEBDK@Z; HashFn::HashString(char const *,ulong)
0x18000bb77  mov     [rdi+100h], eax
0x18000bb7d  mov     rcx, [r8+8]; this
0x18000bb81  test    rcx, rcx
0x18000bb84  jz      short loc_18000BB91
0x18000bb86  call    ?HashString@HashFn@@YAKPEBDK@Z; HashFn::HashString(char const *,ulong)
0x18000bb8b  mov     [rdi+104h], eax
0x18000bb91  call    cs:__imp_GetTickCount64
0x18000bb98  nop     dword ptr [rax+rax+00h]
0x18000bb9d  mov     [rdi+108h], rax
0x18000bba4  test    ebx, ebx
0x18000bba6  jz      short loc_18000BBD2
0x18000bba8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbaf  cmp     rcx, rsi
0x18000bbb2  jz      short loc_18000BBD2
0x18000bbb4  test    byte ptr [rcx+1Ch], 1
0x18000bbb8  jz      short loc_18000BBD2
0x18000bbba  mov     rcx, [rcx+10h]
0x18000bbbe  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000bbc5  mov     edx, 1Dh
0x18000bbca  mov     r9d, ebx
0x18000bbcd  call    WPP_SF_d
0x18000bbd2  mov     rsi, [rsp+28h+arg_8]
0x18000bbd7  mov     eax, ebx
0x18000bbd9  mov     rbx, [rsp+28h+arg_0]
0x18000bbde  add     rsp, 20h
0x18000bbe2  pop     rdi
0x18000bbe3  retn
```
