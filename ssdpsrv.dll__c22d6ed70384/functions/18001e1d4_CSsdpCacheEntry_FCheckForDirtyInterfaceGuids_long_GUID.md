# CSsdpCacheEntry::FCheckForDirtyInterfaceGuids(long,_GUID *)

- ea: `0x18001e1d4`
- end: `0x18001e2c8`
- name: `?FCheckForDirtyInterfaceGuids@CSsdpCacheEntry@@QEAAHJPEAU_GUID@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001e068`

## callees

- `0x1800091ac`
- `0x1800099c8`
- `0x18001e1d4`
- `0x18001e594`
- `0x1800255a8`
- `0x180028000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e2b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e2b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e1f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e1f3`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::FCheckForDirtyInterfaceGuids(CSsdpCacheEntry *this, int a2, struct _GUID *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  unsigned int v7; // ebp
  int i; // ecx
  __int64 v9; // rax
  int v10; // edx
  int v11; // esi

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
        v11 = CSsdpCacheEntry::NotifyForAllAddressFamily(this, v10);
        if ( v11 >= 0 )
          CSsdpCacheEntry::ClearLocationCacheEntry(this);
        if ( v11 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
            (unsigned int)v11);
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
0x18001e1d4  push    rbx
0x18001e1d6  push    rbp
0x18001e1d7  push    rsi
0x18001e1d8  push    rdi
0x18001e1d9  push    r14
0x18001e1db  sub     rsp, 20h
0x18001e1df  lea     rbx, [rcx+0D8h]
0x18001e1e6  mov     rdi, rcx
0x18001e1e9  mov     rcx, rbx; lpCriticalSection
0x18001e1ec  mov     r14, r8
0x18001e1ef  mov     esi, edx
0x18001e1f1  xor     ebp, ebp
0x18001e1f3  call    cs:__imp_EnterCriticalSection
0x18001e1f9  xor     ecx, ecx
0x18001e1fb  cmp     ecx, esi
0x18001e1fd  jge     loc_18001E2B2
0x18001e203  movsxd  rdx, ecx
0x18001e206  add     rdx, rdx
0x18001e209  mov     rax, [r14+rdx*8]
0x18001e20d  sub     rax, [rdi+28h]
0x18001e211  jnz     short loc_18001E21C
0x18001e213  mov     rax, [r14+rdx*8+8]
0x18001e218  sub     rax, [rdi+30h]
0x18001e21c  test    rax, rax
0x18001e21f  jz      short loc_18001E225
0x18001e221  inc     ecx
0x18001e223  jmp     short loc_18001E1FB
0x18001e225  lea     rcx, [rdi+8]; struct _SSDP_REQUEST *
0x18001e229  mov     ebp, 1
0x18001e22e  call    ?ConvertToByebyeNotify@@YAHPEAU_SSDP_REQUEST@@@Z; ConvertToByebyeNotify(_SSDP_REQUEST *)
0x18001e233  test    eax, eax
0x18001e235  jz      short loc_18001E284
0x18001e237  mov     rcx, rdi; this
0x18001e23a  call    ?NotifyForAllAddressFamily@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::NotifyForAllAddressFamily(int)
0x18001e23f  mov     esi, eax
0x18001e241  test    eax, eax
0x18001e243  js      short loc_18001E24D
0x18001e245  mov     rcx, rdi; this
0x18001e248  call    ?ClearLocationCacheEntry@CSsdpCacheEntry@@AEAAXXZ; CSsdpCacheEntry::ClearLocationCacheEntry(void)
0x18001e24d  test    esi, esi
0x18001e24f  jz      short loc_18001E2B2
0x18001e251  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e258  lea     rdx, WPP_GLOBAL_Control
0x18001e25f  cmp     rcx, rdx
0x18001e262  jz      short loc_18001E2B2
0x18001e264  test    [rcx+1Ch], bpl
0x18001e268  jz      short loc_18001E2B2
0x18001e26a  mov     rcx, [rcx+10h]
0x18001e26e  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001e275  mov     edx, 39h ; '9'
0x18001e27a  mov     r9d, esi
0x18001e27d  call    WPP_SF_d
0x18001e282  jmp     short loc_18001E2B2
0x18001e284  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e28b  lea     rdx, WPP_GLOBAL_Control
0x18001e292  cmp     rcx, rdx
0x18001e295  jz      short loc_18001E2B2
0x18001e297  test    [rcx+1Ch], bpl
0x18001e29b  jz      short loc_18001E2B2
0x18001e29d  mov     rcx, [rcx+10h]
0x18001e2a1  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18001e2a8  mov     edx, 38h ; '8'
0x18001e2ad  call    WPP_SF_
0x18001e2b2  mov     rcx, rbx; lpCriticalSection
0x18001e2b5  call    cs:__imp_LeaveCriticalSection
0x18001e2bb  mov     eax, ebp
0x18001e2bd  add     rsp, 20h
0x18001e2c1  pop     r14
0x18001e2c3  pop     rdi
0x18001e2c4  pop     rsi
0x18001e2c5  pop     rbp
0x18001e2c6  pop     rbx
0x18001e2c7  retn
```
