# CSsdpCacheEntry::FCheckForDirtyInterfaceGuids(long,_GUID *)

- ea: `0x18001f6c4`
- end: `0x18001f7c5`
- name: `?FCheckForDirtyInterfaceGuids@CSsdpCacheEntry@@QEAAHJPEAU_GUID@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001f54c`

## callees

- `0x18000a7dc`
- `0x18000af80`
- `0x18001f6c4`
- `0x18001fabc`
- `0x1800271fc`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f7ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f7ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f6e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f6e3`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::FCheckForDirtyInterfaceGuids(CSsdpCacheEntry *this, int a2, struct _GUID *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  unsigned int v7; // ebp
  int i; // ecx
  __int64 v9; // rax
  int v10; // esi

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  for ( i = 0; i < a2; ++i )
  {
    v9 = *(_QWORD *)&a3[i].Data1 - *((_QWORD *)this + 5);
    if ( !v9 )
      v9 = *(_QWORD *)a3[i].Data4 - *((_QWORD *)this + 6);
    if ( !v9 )
    {
      v7 = 1;
      if ( (unsigned int)ConvertToByebyeNotify((CSsdpCacheEntry *)((char *)this + 8)) )
      {
        v10 = CSsdpCacheEntry::NotifyForAllAddressFamily(this);
        if ( v10 >= 0 )
          CSsdpCacheEntry::ClearLocationCacheEntry(this);
        if ( v10 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
            (unsigned int)v10);
      }
      else if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids);
      }
      break;
    }
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18001f6c4  push    rbx
0x18001f6c6  push    rbp
0x18001f6c7  push    rsi
0x18001f6c8  push    rdi
0x18001f6c9  push    r14
0x18001f6cb  sub     rsp, 20h
0x18001f6cf  lea     rbx, [rcx+0D8h]
0x18001f6d6  mov     rdi, rcx
0x18001f6d9  mov     rcx, rbx; lpCriticalSection
0x18001f6dc  mov     r14, r8
0x18001f6df  mov     esi, edx
0x18001f6e1  xor     ebp, ebp
0x18001f6e3  call    cs:__imp_EnterCriticalSection
0x18001f6ea  nop     dword ptr [rax+rax+00h]
0x18001f6ef  xor     ecx, ecx
0x18001f6f1  cmp     ecx, esi
0x18001f6f3  jge     loc_18001F7A8
0x18001f6f9  movsxd  rdx, ecx
0x18001f6fc  add     rdx, rdx
0x18001f6ff  mov     rax, [r14+rdx*8]
0x18001f703  sub     rax, [rdi+28h]
0x18001f707  jnz     short loc_18001F712
0x18001f709  mov     rax, [r14+rdx*8+8]
0x18001f70e  sub     rax, [rdi+30h]
0x18001f712  test    rax, rax
0x18001f715  jz      short loc_18001F71B
0x18001f717  inc     ecx
0x18001f719  jmp     short loc_18001F6F1
0x18001f71b  lea     rcx, [rdi+8]; struct _SSDP_REQUEST *
0x18001f71f  mov     ebp, 1
0x18001f724  call    ?ConvertToByebyeNotify@@YAHPEAU_SSDP_REQUEST@@@Z; ConvertToByebyeNotify(_SSDP_REQUEST *)
0x18001f729  test    eax, eax
0x18001f72b  jz      short loc_18001F77A
0x18001f72d  mov     rcx, rdi; this
0x18001f730  call    ?NotifyForAllAddressFamily@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::NotifyForAllAddressFamily(int)
0x18001f735  mov     esi, eax
0x18001f737  test    eax, eax
0x18001f739  js      short loc_18001F743
0x18001f73b  mov     rcx, rdi; this
0x18001f73e  call    ?ClearLocationCacheEntry@CSsdpCacheEntry@@AEAAXXZ; CSsdpCacheEntry::ClearLocationCacheEntry(void)
0x18001f743  test    esi, esi
0x18001f745  jz      short loc_18001F7A8
0x18001f747  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f74e  lea     rdx, WPP_GLOBAL_Control
0x18001f755  cmp     rcx, rdx
0x18001f758  jz      short loc_18001F7A8
0x18001f75a  test    [rcx+1Ch], bpl
0x18001f75e  jz      short loc_18001F7A8
0x18001f760  mov     rcx, [rcx+10h]
0x18001f764  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001f76b  mov     edx, 39h ; '9'
0x18001f770  mov     r9d, esi
0x18001f773  call    WPP_SF_d
0x18001f778  jmp     short loc_18001F7A8
0x18001f77a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f781  lea     rdx, WPP_GLOBAL_Control
0x18001f788  cmp     rcx, rdx
0x18001f78b  jz      short loc_18001F7A8
0x18001f78d  test    [rcx+1Ch], bpl
0x18001f791  jz      short loc_18001F7A8
0x18001f793  mov     rcx, [rcx+10h]
0x18001f797  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001f79e  mov     edx, 38h ; '8'
0x18001f7a3  call    WPP_SF_
0x18001f7a8  mov     rcx, rbx; lpCriticalSection
0x18001f7ab  call    cs:__imp_LeaveCriticalSection
0x18001f7b2  nop     dword ptr [rax+rax+00h]
0x18001f7b7  mov     eax, ebp
0x18001f7b9  add     rsp, 20h
0x18001f7bd  pop     r14
0x18001f7bf  pop     rdi
0x18001f7c0  pop     rsi
0x18001f7c1  pop     rbp
0x18001f7c2  pop     rbx
0x18001f7c3  retn
```
