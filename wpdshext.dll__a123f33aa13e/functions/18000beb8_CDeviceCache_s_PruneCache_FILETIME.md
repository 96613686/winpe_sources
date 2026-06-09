# CDeviceCache::s_PruneCache(_FILETIME)

- ea: `0x18000beb8`
- end: `0x18000bff8`
- name: `?s_PruneCache@CDeviceCache@@CAJU_FILETIME@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(struct _FILETIME)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ba84`

## callees

- `0x18000beb8`
- `0x18000c150`
- `0x18000cb90`
- `0x18001d6b0`
- `0x180039d74`
- `0x1800554bc`
- `0x180055a6c`
- `0x18006b954`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000bed8`
- `KERNEL32!EnterCriticalSection` at `0x18000bed8`
- `KERNEL32!LeaveCriticalSection` at `0x18000bfdb`
- `KERNEL32!LeaveCriticalSection` at `0x18000bfdb`
- `KERNEL32!CompareFileTime` at `0x18000bf24`
- `KERNEL32!CompareFileTime` at `0x18000bf24`

## pseudocode

```c
__int64 __fastcall CDeviceCache::s_PruneCache(FILETIME a1, __int64 a2, __int64 a3)
{
  struct CDeviceCache *v3; // rax
  unsigned int i; // ebx
  _DWORD *v5; // rcx
  int v6; // eax
  const FILETIME *Ptr; // rax
  const FILETIME *v8; // rsi
  int j; // edi
  _DWORD *v10; // rcx
  int v11; // eax
  const void *v12; // rax
  DEVITEM_CACHE *v13; // rax
  unsigned int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  FILETIME FileTime1; // [rsp+30h] [rbp+8h] BYREF

  FileTime1 = a1;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))DllAddRef)(a1, a2, a3);
  EnterCriticalSection(&g_csDeviceCache);
  v3 = g_pDeviceCache;
  if ( g_pDeviceCache )
  {
    for ( i = 0; ; ++i )
    {
      v5 = (_DWORD *)*((_QWORD *)v3 + 1);
      v6 = v5 ? *v5 : 0;
      if ( (int)i >= v6 )
        break;
      Ptr = (const FILETIME *)IsolationAwareDPA_GetPtr(v5, (int)i);
      v8 = Ptr;
      if ( Ptr && CompareFileTime(&FileTime1, Ptr + 1) > 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_S)(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids,
            *v8);
        if ( v8[3] )
        {
          for ( j = 0; ; ++j )
          {
            v10 = (_DWORD *)v8[3];
            v11 = v10 ? *v10 : 0;
            if ( j >= v11 )
              break;
            v12 = (const void *)IsolationAwareDPA_GetPtr(v10, j);
            if ( v12 )
              ChangeNotify(128, 0x3000u, v12, 0);
          }
        }
        v13 = (DEVITEM_CACHE *)IsolationAwareDPA_DeletePtr(*((_QWORD *)g_pDeviceCache + 1), i);
        if ( v13 )
        {
          DEVITEM_CACHE::`scalar deleting destructor'(v13, v14);
          --i;
        }
      }
      v3 = g_pDeviceCache;
    }
  }
  LeaveCriticalSection(&g_csDeviceCache);
  DllRelease(v16, v15, v17);
  return 0;
}

```

## disassembly

```asm
0x18000beb8  mov     [rsp+arg_8], rbx
0x18000bebd  mov     [rsp+arg_10], rsi
0x18000bec2  mov     qword ptr [rsp+FileTime1.dwLowDateTime], rcx
0x18000bec7  push    rdi
0x18000bec8  sub     rsp, 20h
0x18000becc  call    DllAddRef
0x18000bed1  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000bed8  call    cs:__imp_EnterCriticalSection
0x18000bede  mov     rax, cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA; CDeviceCache * g_pDeviceCache
0x18000bee5  test    rax, rax
0x18000bee8  jz      loc_18000BFD4
0x18000beee  xor     ebx, ebx
0x18000bef0  mov     rcx, [rax+8]
0x18000bef4  test    rcx, rcx
0x18000bef7  jz      short loc_18000BEFD
0x18000bef9  mov     eax, [rcx]
0x18000befb  jmp     short loc_18000BEFF
0x18000befd  xor     eax, eax
0x18000beff  cmp     ebx, eax
0x18000bf01  jge     loc_18000BFD4
0x18000bf07  movsxd  rdx, ebx
0x18000bf0a  call    IsolationAwareDPA_GetPtr
0x18000bf0f  mov     rsi, rax
0x18000bf12  test    rax, rax
0x18000bf15  jz      loc_18000BFC6
0x18000bf1b  lea     rdx, [rax+8]; lpFileTime2
0x18000bf1f  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x18000bf24  call    cs:__imp_CompareFileTime
0x18000bf2a  test    eax, eax
0x18000bf2c  jle     loc_18000BFC6
0x18000bf32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf39  lea     rax, WPP_GLOBAL_Control
0x18000bf40  cmp     rcx, rax
0x18000bf43  jz      short loc_18000BF63
0x18000bf45  test    byte ptr [rcx+1Ch], 40h
0x18000bf49  jz      short loc_18000BF63
0x18000bf4b  mov     r9, [rsi]
0x18000bf4e  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000bf55  mov     rcx, [rcx+10h]
0x18000bf59  mov     edx, 18h
0x18000bf5e  call    WPP_SF_S
0x18000bf63  cmp     qword ptr [rsi+18h], 0
0x18000bf68  jz      short loc_18000BFA5
0x18000bf6a  xor     edi, edi
0x18000bf6c  mov     rcx, [rsi+18h]
0x18000bf70  test    rcx, rcx
0x18000bf73  jz      short loc_18000BF79
0x18000bf75  mov     eax, [rcx]
0x18000bf77  jmp     short loc_18000BF7B
0x18000bf79  xor     eax, eax
0x18000bf7b  cmp     edi, eax
0x18000bf7d  jge     short loc_18000BFA5
0x18000bf7f  movsxd  rdx, edi
0x18000bf82  call    IsolationAwareDPA_GetPtr
0x18000bf87  test    rax, rax
0x18000bf8a  jz      short loc_18000BFA1
0x18000bf8c  xor     r9d, r9d; dwItem2
0x18000bf8f  mov     r8, rax; dwItem1
0x18000bf92  mov     edx, 3000h; uFlags
0x18000bf97  mov     ecx, 80h; wEventId
0x18000bf9c  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18000bfa1  inc     edi
0x18000bfa3  jmp     short loc_18000BF6C
0x18000bfa5  mov     rcx, cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA; CDeviceCache * g_pDeviceCache
0x18000bfac  mov     edx, ebx
0x18000bfae  mov     rcx, [rcx+8]
0x18000bfb2  call    IsolationAwareDPA_DeletePtr
0x18000bfb7  test    rax, rax
0x18000bfba  jz      short loc_18000BFC6
0x18000bfbc  mov     rcx, rax; this
0x18000bfbf  call    ??_GDEVITEM_CACHE@@QEAAPEAXI@Z; DEVITEM_CACHE::`scalar deleting destructor'(uint)
0x18000bfc4  dec     ebx
0x18000bfc6  mov     rax, cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA; CDeviceCache * g_pDeviceCache
0x18000bfcd  inc     ebx
0x18000bfcf  jmp     loc_18000BEF0
0x18000bfd4  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000bfdb  call    cs:__imp_LeaveCriticalSection
0x18000bfe1  call    DllRelease
0x18000bfe6  mov     rbx, [rsp+28h+arg_8]
0x18000bfeb  xor     eax, eax
0x18000bfed  mov     rsi, [rsp+28h+arg_10]
0x18000bff2  add     rsp, 20h
0x18000bff6  pop     rdi
0x18000bff7  retn
```
