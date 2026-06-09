# DllMain_Msdatl(HINSTANCE__ *,ulong,void *)

- ea: `0x383a98d00`
- end: `0x383a98e16`
- name: `?DllMain_Msdatl@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `278`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x3839af4b0`

## callees

- `0x383895d70`
- `0x383895dbc`
- `0x383a98d00`
- `0x383a9cc40`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x383a98db8`
- `KERNEL32!VirtualFree` at `0x383a98db8`
- `KERNEL32!InterlockedPopEntrySList` at `0x383a98dc2`
- `KERNEL32!InterlockedPopEntrySList` at `0x383a98dc2`
- `KERNEL32!InitializeSListHead` at `0x383a98d8d`
- `KERNEL32!InitializeSListHead` at `0x383a98d8d`
- `ole32!CoGetMalloc` at `0x383a98d2b`
- `ole32!CoGetMalloc` at `0x383a98d2b`

## pseudocode

```c
__int64 __fastcall DllMain_Msdatl(HINSTANCE a1, __int64 a2, void *a3)
{
  unsigned int v3; // ebx
  HRESULT Malloc; // eax
  union _SLIST_HEADER *v5; // rax
  union _SLIST_HEADER *v6; // rdi
  PSLIST_ENTRY v7; // rax

  v3 = 0;
  if ( (_DWORD)a1 )
  {
    if ( (_DWORD)a1 == 1 )
    {
      Malloc = CoGetMalloc(1u, &g_pIMalloc);
      if ( g_pIMalloc )
      {
        if ( Malloc >= 0 )
        {
          v3 = InitializeVLHeapPool();
          if ( v3 )
          {
            v5 = (union _SLIST_HEADER *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(
                                          g_pMO,
                                          32);
            if ( v5 )
              v5 = (union _SLIST_HEADER *)CReservedBlockManager::CReservedBlockManager((CReservedBlockManager *)v5);
            CReservedBlockManager::s_pInstance = (struct CReservedBlockManager *)v5;
            if ( v5 )
            {
              InitializeSListHead(v5 + 1);
              return 1;
            }
            else
            {
              v3 = 0;
              UninitializeVLHeapPool();
            }
          }
        }
      }
    }
  }
  else
  {
    v6 = (union _SLIST_HEADER *)CReservedBlockManager::s_pInstance;
    v3 = 1;
    if ( CReservedBlockManager::s_pInstance )
    {
      while ( 1 )
      {
        v7 = InterlockedPopEntrySList(v6 + 1);
        if ( !v7 )
          break;
        VirtualFree(v7, 0, 0x8000u);
      }
      ((void (__fastcall *)(struct IMalloc *, union _SLIST_HEADER *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v6);
    }
    CReservedBlockManager::s_pInstance = 0;
    UninitializeVLHeapPool();
    if ( g_pIMalloc )
    {
      ((void (__fastcall *)(LPMALLOC))g_pIMalloc->lpVtbl->Release)(g_pIMalloc);
      g_pIMalloc = 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x383a98d00  mov     [rsp+arg_0], rbx
0x383a98d05  mov     [rsp+arg_8], rsi
0x383a98d0a  push    rdi
0x383a98d0b  sub     rsp, 20h
0x383a98d0f  xor     ebx, ebx
0x383a98d11  test    ecx, ecx
0x383a98d13  jz      loc_383A98D9A
0x383a98d19  dec     ecx
0x383a98d1b  jnz     loc_383A98E04
0x383a98d21  lea     rdx, ?g_pIMalloc@@3PEAUIMalloc@@EA; ppMalloc
0x383a98d28  lea     ecx, [rbx+1]; dwMemContext
0x383a98d2b  call    cs:__imp_CoGetMalloc
0x383a98d31  cmp     cs:?g_pIMalloc@@3PEAUIMalloc@@EA, rbx; IMalloc * g_pIMalloc
0x383a98d38  jz      loc_383A98E04
0x383a98d3e  test    eax, eax
0x383a98d40  js      loc_383A98E04
0x383a98d46  call    ?InitializeVLHeapPool@@YAHXZ; InitializeVLHeapPool(void)
0x383a98d4b  mov     ebx, eax
0x383a98d4d  test    eax, eax
0x383a98d4f  jz      loc_383A98E04
0x383a98d55  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98d5c  mov     edx, 20h ; ' '
0x383a98d61  mov     rax, [rcx]
0x383a98d64  call    qword ptr [rax+58h]
0x383a98d67  test    rax, rax
0x383a98d6a  jz      short loc_383A98D74
0x383a98d6c  mov     rcx, rax; this
0x383a98d6f  call    ??0CReservedBlockManager@@IEAA@XZ; CReservedBlockManager::CReservedBlockManager(void)
0x383a98d74  mov     cs:?s_pInstance@CReservedBlockManager@@1PEAV1@EA, rax; CReservedBlockManager * CReservedBlockManager::s_pInstance
0x383a98d7b  test    rax, rax
0x383a98d7e  jnz     short loc_383A98D89
0x383a98d80  xor     ebx, ebx
0x383a98d82  call    ?UninitializeVLHeapPool@@YAXXZ; UninitializeVLHeapPool(void)
0x383a98d87  jmp     short loc_383A98E04
0x383a98d89  lea     rcx, [rax+10h]; ListHead
0x383a98d8d  call    cs:__imp_InitializeSListHead
0x383a98d93  mov     ebx, 1
0x383a98d98  jmp     short loc_383A98E04
0x383a98d9a  mov     rdi, cs:?s_pInstance@CReservedBlockManager@@1PEAV1@EA; CReservedBlockManager * CReservedBlockManager::s_pInstance
0x383a98da1  mov     ebx, 1
0x383a98da6  test    rdi, rdi
0x383a98da9  jz      short loc_383A98DDD
0x383a98dab  jmp     short loc_383A98DBE
0x383a98dad  xor     edx, edx; dwSize
0x383a98daf  mov     r8d, 8000h; dwFreeType
0x383a98db5  mov     rcx, rax; lpAddress
0x383a98db8  call    cs:__imp_VirtualFree
0x383a98dbe  lea     rcx, [rdi+10h]; ListHead
0x383a98dc2  call    cs:__imp_InterlockedPopEntrySList
0x383a98dc8  test    rax, rax
0x383a98dcb  jnz     short loc_383A98DAD
0x383a98dcd  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98dd4  mov     rdx, rdi
0x383a98dd7  mov     rax, [rcx]
0x383a98dda  call    qword ptr [rax+68h]
0x383a98ddd  and     cs:?s_pInstance@CReservedBlockManager@@1PEAV1@EA, 0; CReservedBlockManager * CReservedBlockManager::s_pInstance
0x383a98de5  call    ?UninitializeVLHeapPool@@YAXXZ; UninitializeVLHeapPool(void)
0x383a98dea  mov     rcx, cs:?g_pIMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pIMalloc
0x383a98df1  test    rcx, rcx
0x383a98df4  jz      short loc_383A98E04
0x383a98df6  mov     rax, [rcx]
0x383a98df9  call    qword ptr [rax+10h]
0x383a98dfc  and     cs:?g_pIMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pIMalloc
0x383a98e04  mov     rsi, [rsp+28h+arg_8]
0x383a98e09  mov     eax, ebx
0x383a98e0b  mov     rbx, [rsp+28h+arg_0]
0x383a98e10  add     rsp, 20h
0x383a98e14  pop     rdi
0x383a98e15  retn
```
