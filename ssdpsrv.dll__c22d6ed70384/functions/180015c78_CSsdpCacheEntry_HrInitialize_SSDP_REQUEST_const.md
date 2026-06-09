# CSsdpCacheEntry::HrInitialize(_SSDP_REQUEST const *)

- ea: `0x180015c78`
- end: `0x180015d5e`
- name: `?HrInitialize@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(struct _NETWORK_LOCATION_INFO **this, const struct _SSDP_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180003a00`

## callees

- `0x180006eb8`
- `0x180008610`
- `0x180015c78`
- `0x180015d70`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180015d11`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180015d11`

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
0x180015c78  mov     [rsp+arg_0], rbx
0x180015c7d  mov     [rsp+arg_8], rsi
0x180015c82  push    rdi
0x180015c83  sub     rsp, 20h
0x180015c87  mov     rdi, rcx
0x180015c8a  add     rcx, 8; struct _SSDP_REQUEST *
0x180015c8e  call    ?CopySsdpRequest@@YAHPEAU_SSDP_REQUEST@@PEBU1@@Z; CopySsdpRequest(_SSDP_REQUEST *,_SSDP_REQUEST const *)
0x180015c93  lea     rsi, WPP_GLOBAL_Control
0x180015c9a  test    eax, eax
0x180015c9c  jnz     short loc_180015CD1
0x180015c9e  mov     ebx, 80004005h
0x180015ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x180015caa  cmp     rcx, rsi
0x180015cad  jz      loc_180015D4C
0x180015cb3  test    byte ptr [rcx+1Ch], 1
0x180015cb7  jz      short loc_180015D29
0x180015cb9  mov     rcx, [rcx+10h]
0x180015cbd  lea     edx, [rax+1Ch]
0x180015cc0  mov     r9d, ebx
0x180015cc3  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180015cca  call    WPP_SF_d
0x180015ccf  jmp     short loc_180015D22
0x180015cd1  xor     r8d, r8d; int *
0x180015cd4  xor     edx, edx; int *
0x180015cd6  mov     rcx, rdi; this
0x180015cd9  call    ?UpdateLocationCacheEntry@CSsdpCacheEntry@@AEAAJPEAH0@Z; CSsdpCacheEntry::UpdateLocationCacheEntry(int *,int *)
0x180015cde  mov     r8, [rdi+58h]; unsigned int
0x180015ce2  mov     ebx, eax
0x180015ce4  test    r8, r8
0x180015ce7  jz      short loc_180015D11
0x180015ce9  mov     rcx, [r8+40h]; this
0x180015ced  test    rcx, rcx
0x180015cf0  jz      short loc_180015CFD
0x180015cf2  call    ?HashString@HashFn@@YAKPEBDK@Z; HashFn::HashString(char const *,ulong)
0x180015cf7  mov     [rdi+100h], eax
0x180015cfd  mov     rcx, [r8+8]; this
0x180015d01  test    rcx, rcx
0x180015d04  jz      short loc_180015D11
0x180015d06  call    ?HashString@HashFn@@YAKPEBDK@Z; HashFn::HashString(char const *,ulong)
0x180015d0b  mov     [rdi+104h], eax
0x180015d11  call    cs:__imp_GetTickCount64
0x180015d17  mov     [rdi+108h], rax
0x180015d1e  test    ebx, ebx
0x180015d20  jz      short loc_180015D4C
0x180015d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d29  cmp     rcx, rsi
0x180015d2c  jz      short loc_180015D4C
0x180015d2e  test    byte ptr [rcx+1Ch], 1
0x180015d32  jz      short loc_180015D4C
0x180015d34  mov     rcx, [rcx+10h]
0x180015d38  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180015d3f  mov     edx, 1Dh
0x180015d44  mov     r9d, ebx
0x180015d47  call    WPP_SF_d
0x180015d4c  mov     rsi, [rsp+28h+arg_8]
0x180015d51  mov     eax, ebx
0x180015d53  mov     rbx, [rsp+28h+arg_0]
0x180015d58  add     rsp, 20h
0x180015d5c  pop     rdi
0x180015d5d  retn
```
