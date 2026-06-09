# MemoryNode::BootInit(void)

- ea: `0x1004a07e0`
- end: `0x1004a0bb9`
- name: `?BootInit@MemoryNode@@QEAAXXZ`
- size: `985`
- prototype: `void __fastcall(MemoryNode *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1004afc30`
- `0x1004b0cd0`
- `0x1004b2e10`

## callees

- `0x100403070`
- `0x10040e320`
- `0x1004975e0`
- `0x1004a07e0`

## import_xrefs

- `KERNEL32!AllocateUserPhysicalPagesNuma` at `0x1004a0990`
- `KERNEL32!VirtualAllocExNuma` at `0x1004a09a5`
- `KERNEL32!GetSystemInfo` at `0x1004a08d7`
- `KERNEL32!GetSystemInfo` at `0x1004a08d7`
- `KERNEL32!LoadLibraryExW` at `0x1004a0b47`
- `KERNEL32!LoadLibraryExW` at `0x1004a0b47`
- `KERNEL32!GetModuleHandleW` at `0x1004a09b3`
- `KERNEL32!GetModuleHandleW` at `0x1004a09b3`
- `KERNEL32!GetProcAddress` at `0x1004a09c3`
- `KERNEL32!GetProcAddress` at `0x1004a0b5c`
- `KERNEL32!GetProcAddress` at `0x1004a09c3`
- `KERNEL32!GetProcAddress` at `0x1004a0b5c`
- `KERNEL32!GetLastError` at `0x1004a0b6e`
- `KERNEL32!GetLastError` at `0x1004a0b7d`
- `KERNEL32!GetLastError` at `0x1004a0b6e`
- `KERNEL32!GetLastError` at `0x1004a0b7d`

## string_xrefs

- `0x1004a0997`: `ntdll.dll`
- `0x1004a0b3a`: `dkdll.dll`
- `0x1004a0b83`: `Failed to load dkdll.dll with %d.\n`

## pseudocode

```c
void __fastcall MemoryNode::BootInit(MemoryNode *this)
{
  unsigned __int16 v2; // cx
  int v3; // r8d
  unsigned __int64 *v4; // r9
  __int64 v5; // r10
  unsigned __int64 v6; // rdx
  HMODULE ModuleHandleW; // rax
  unsigned __int8 *Buffer; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r9
  char *v11; // rdx
  unsigned __int8 *v12; // r8
  __int64 v13; // r8
  HMODULE Library; // rax
  DWORD LastError; // eax
  const wchar_t *v16; // rcx
  void (*v17)(const wchar_t *, ...); // r8
  struct _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-D8h] BYREF
  _OWORD v19[8]; // [rsp+50h] [rbp-A8h] BYREF

  if ( (SOS_PublicGlobals::sm_osStatus & 0x100) == 0
    && !MemoryNode::sm_VirtualAllocExNuma
    && !MemoryNode::sm_AllocateUserPhysicalPagesNuma
    && !MemoryNode::sm_NtAllocateUserPhysicalPagesEx )
  {
    memset(v19, 0, sizeof(v19));
    if ( !(*(unsigned int (__fastcall **)(struct OsNumaConfig *, _OWORD *))(*(_QWORD *)OsNumaConfig::sm_instance + 88LL))(
            OsNumaConfig::sm_instance,
            v19) )
      goto LABEL_13;
    v2 = 0;
    while ( !*((_QWORD *)v19 + v2) )
    {
      if ( ++v2 >= 0x10u )
        goto LABEL_13;
    }
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    v3 = 0;
    v4 = (unsigned __int64 *)v19;
    v5 = 16;
    do
    {
      v6 = *v4++;
      v3 += (unsigned int)((0x101010101010101LL
                          * ((((v6 - ((v6 >> 1) & 0x5555555555555555LL)) & 0x3333333333333333LL)
                            + (((v6 - ((v6 >> 1) & 0x5555555555555555LL)) >> 2) & 0x3333333333333333LL)
                            + ((((v6 - ((v6 >> 1) & 0x5555555555555555LL)) & 0x3333333333333333LL)
                              + (((v6 - ((v6 >> 1) & 0x5555555555555555LL)) >> 2) & 0x3333333333333333LL)) >> 4))
                           & 0xF0F0F0F0F0F0F0FLL)) >> 32) >> 24;
      --v5;
    }
    while ( v5 );
    if ( SystemInfo.dwNumberOfProcessors == v3 )
    {
LABEL_13:
      if ( !byte_100713B81 )
      {
        MemoryNode::sm_AllocateUserPhysicalPagesNuma = (int (*)(void *, unsigned __int64 *, unsigned __int64 *, unsigned int))AllocateUserPhysicalPagesNuma;
        MemoryNode::sm_VirtualAllocExNumaLarge = (void *(*)(void *, void *, unsigned __int64, unsigned int, unsigned int, unsigned int))VirtualAllocExNuma;
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        MemoryNode::sm_NtAllocateUserPhysicalPagesEx = (int (*)(void *, unsigned __int64 *, unsigned __int64 *, struct MEM_EXTENDED_PARAMETER *, unsigned int))GetProcAddress(ModuleHandleW, "NtAllocateUserPhysicalPagesEx");
      }
    }
  }
  if ( (SOS_PublicGlobals::sm_osStatus & 0x10) != 0 )
  {
    if ( MemoryNode_LargePageSize )
    {
      if ( SOS_OS_MemoryModel != 1 )
      {
        Buffer = (unsigned __int8 *)_InterlockedExchange64(
                                      (volatile __int64 *)&(&LargePageAllocator::sm_perNodePreAllocation)[*((unsigned __int16 *)this + 64)],
                                      0);
        if ( Buffer || (Buffer = LargePageAllocator::AllocateBuffer(this)) != 0 )
        {
          v9 = MemoryNode_LargePageSize;
          *((_QWORD *)this + 25) = Buffer;
          *((_DWORD *)this + 49) = 0;
          v10 = v9 + 0x1FFFFFF - (v9 + 0x1FFFFFF) % v9;
          v11 = (char *)this + 224;
          *((_QWORD *)this + 29) = (char *)this + 224;
          *((_QWORD *)this + 28) = (char *)this + 224;
          *((_QWORD *)this + 26) = v10;
          v12 = &Buffer[v10];
          if ( Buffer < &Buffer[v10] )
          {
            _mm_lfence();
            do
            {
              *(_QWORD *)Buffer = 0;
              *((_QWORD *)Buffer + 1) = 0;
              *(_QWORD *)Buffer = *(_QWORD *)v11;
              *(_QWORD *)(*(_QWORD *)v11 + 8LL) = Buffer;
              *(_QWORD *)v11 = Buffer;
              *((_QWORD *)Buffer + 1) = v11;
              Buffer += 0x2000;
              ++*((_QWORD *)this + 23);
            }
            while ( Buffer < v12 );
          }
          *((_DWORD *)this + 48) = 1;
        }
      }
    }
  }
  else
  {
    MemoryNode_LargePageSize = 0;
  }
  if ( !*((_DWORD *)this + 12) )
  {
    _InterlockedExchangeAdd64((volatile signed __int64 *)this + 7, 0x100u);
    _InterlockedExchangeAdd64((volatile signed __int64 *)this + 8, 0x100u);
    if ( dword_100720F58 != 1 )
    {
      v13 = *((_QWORD *)this + 21);
      if ( v13 >= *((_QWORD *)this + 18) )
        v13 = *((_QWORD *)this + 18);
      if ( v13 == (*((_QWORD *)this + 8) + *((_QWORD *)this + 9) + *((_QWORD *)this + 10) + 1LL) / 2 )
        MemoryNode::RecalculateTarget();
    }
  }
  if ( byte_100713B81 )
  {
    Library = LoadLibraryExW(L"dkdll.dll", 0, 0x800u);
    if ( Library )
    {
      MemoryNode::sm_NtMapViewOfFileExNumaProtection = (void *(*)(void *, unsigned int, unsigned int, unsigned int, unsigned __int64, void *, unsigned int, unsigned int *))GetProcAddress(Library, "NtMapViewOfFileExNumaProtection");
      if ( MemoryNode::sm_NtMapViewOfFileExNumaProtection )
        return;
      LastError = GetLastError();
      v16 = L"Failed to retrieve the address of NtMapViewOfFileExNumaProtection function with %d.\n";
    }
    else
    {
      LastError = GetLastError();
      v16 = L"Failed to load dkdll.dll with %d.\n";
    }
    v17 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
    if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
      v17 = SOS_OS_LogUnlocalizedRoutine;
    v17(v16, LastError);
  }
}

```

## disassembly

```asm
0x1004a07e0  mov     r11, rsp
0x1004a07e3  sub     rsp, 0F8h
0x1004a07ea  mov     rax, cs:__security_cookie
0x1004a07f1  xor     rax, rsp
0x1004a07f4  mov     [rsp+0F8h+var_28], rax
0x1004a07fc  mov     [r11+10h], rbx
0x1004a0800  mov     rbx, rcx
0x1004a0803  mov     [r11+20h], rsi
0x1004a0807  xor     esi, esi
0x1004a0809  mov     [r11-8], rdi
0x1004a080d  mov     edi, 100h
0x1004a0812  test    cs:?sm_osStatus@SOS_PublicGlobals@@2KA, edi; ulong SOS_PublicGlobals::sm_osStatus
0x1004a0818  jnz     loc_1004A09D0
0x1004a081e  cmp     cs:?sm_VirtualAllocExNuma@MemoryNode@@0P6APEAXPEAX0_KKKK@ZEA, rsi; void * (*MemoryNode::sm_VirtualAllocExNuma)(void *,void *,unsigned __int64,ulong,ulong,ulong)
0x1004a0825  jnz     loc_1004A09D0
0x1004a082b  cmp     cs:?sm_AllocateUserPhysicalPagesNuma@MemoryNode@@0P6AHPEAXPEA_K1K@ZEA, rsi; int (*MemoryNode::sm_AllocateUserPhysicalPagesNuma)(void *,unsigned __int64 *,unsigned __int64 *,ulong)
0x1004a0832  jnz     loc_1004A09D0
0x1004a0838  cmp     cs:?sm_NtAllocateUserPhysicalPagesEx@MemoryNode@@0P6AJPEAXPEA_K1PEAUMEM_EXTENDED_PARAMETER@@K@ZEA, rsi; long (*MemoryNode::sm_NtAllocateUserPhysicalPagesEx)(void *,unsigned __int64 *,unsigned __int64 *,MEM_EXTENDED_PARAMETER *,ulong)
0x1004a083f  jnz     loc_1004A09D0
0x1004a0845  mov     rcx, cs:?sm_instance@OsNumaConfig@@0PEAV1@EA; OsNumaConfig * OsNumaConfig::sm_instance
0x1004a084c  lea     rdx, [rsp+0F8h+var_A8]
0x1004a0851  xorps   xmm0, xmm0
0x1004a0854  movups  [rsp+0F8h+var_A8], xmm0
0x1004a0859  mov     rax, [rcx]
0x1004a085c  movups  [rsp+0F8h+var_98], xmm0
0x1004a0861  movups  [rsp+0F8h+var_88], xmm0
0x1004a0866  movups  xmmword ptr [r11-78h], xmm0
0x1004a086b  movups  xmmword ptr [r11-68h], xmm0
0x1004a0870  movups  xmmword ptr [r11-58h], xmm0
0x1004a0875  movups  xmmword ptr [r11-48h], xmm0
0x1004a087a  movups  xmmword ptr [r11-38h], xmm0
0x1004a087f  call    qword ptr [rax+58h]
0x1004a0882  test    eax, eax
0x1004a0884  jz      loc_1004A0987
0x1004a088a  movzx   ecx, si
0x1004a088d  nop     dword ptr [rax]
0x1004a0890  movzx   eax, cx
0x1004a0893  cmp     qword ptr [rsp+rax*8+0F8h+var_A8], rsi
0x1004a0898  jnz     short loc_1004A08A8
0x1004a089a  inc     cx
0x1004a089d  cmp     cx, 10h
0x1004a08a1  jb      short loc_1004A0890
0x1004a08a3  jmp     loc_1004A0987
0x1004a08a8  xorps   xmm0, xmm0
0x1004a08ab  mov     [rsp+0F8h+arg_10], rbp
0x1004a08b3  mov     [rsp+0F8h+var_10], r14
0x1004a08bb  lea     rcx, [rsp+0F8h+SystemInfo]; lpSystemInfo
0x1004a08c0  mov     [rsp+0F8h+var_18], r15
0x1004a08c8  movups  xmmword ptr [rsp+0F8h+SystemInfo], xmm0
0x1004a08cd  movups  xmmword ptr [rsp+0F8h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1004a08d2  movups  xmmword ptr [rsp+0F8h+SystemInfo.dwNumberOfProcessors], xmm0
0x1004a08d7  call    cs:__imp_GetSystemInfo
0x1004a08dd  mov     r8d, esi
0x1004a08e0  lea     r9, [rsp+0F8h+var_A8]
0x1004a08e5  mov     r10d, 10h
0x1004a08eb  mov     r11, 3333333333333333h
0x1004a08f5  mov     rbp, 5555555555555555h
0x1004a08ff  mov     r14, 0F0F0F0F0F0F0F0Fh
0x1004a0909  mov     r15, 101010101010101h
0x1004a0913  nop     dword ptr [rax+00h]
0x1004a0917  nop     word ptr [rax+rax+00000000h]
0x1004a0920  mov     rdx, [r9]
0x1004a0923  lea     r9, [r9+8]
0x1004a0927  mov     rax, rdx
0x1004a092a  shr     rax, 1
0x1004a092d  and     rax, rbp
0x1004a0930  sub     rdx, rax
0x1004a0933  mov     rcx, rdx
0x1004a0936  and     rdx, r11
0x1004a0939  shr     rcx, 2
0x1004a093d  and     rcx, r11
0x1004a0940  add     rcx, rdx
0x1004a0943  mov     rax, rcx
0x1004a0946  shr     rax, 4
0x1004a094a  add     rax, rcx
0x1004a094d  and     rax, r14
0x1004a0950  imul    rax, r15
0x1004a0954  shr     rax, 38h
0x1004a0958  add     r8d, eax
0x1004a095b  sub     r10, 1
0x1004a095f  jnz     short loc_1004A0920
0x1004a0961  cmp     [rsp+0F8h+SystemInfo.dwNumberOfProcessors], r8d
0x1004a0966  mov     eax, esi
0x1004a0968  mov     r15, [rsp+0F8h+var_18]
0x1004a0970  mov     r14, [rsp+0F8h+var_10]
0x1004a0978  setnz   al
0x1004a097b  mov     rbp, [rsp+0F8h+arg_10]
0x1004a0983  test    eax, eax
0x1004a0985  jnz     short loc_1004A09D0
0x1004a0987  cmp     cs:byte_100713B81, sil
0x1004a098e  jnz     short loc_1004A09D0
0x1004a0990  mov     rax, cs:__imp_AllocateUserPhysicalPagesNuma
0x1004a0997  lea     rcx, ModuleName; "ntdll.dll"
0x1004a099e  mov     cs:?sm_AllocateUserPhysicalPagesNuma@MemoryNode@@0P6AHPEAXPEA_K1K@ZEA, rax; int (*MemoryNode::sm_AllocateUserPhysicalPagesNuma)(void *,unsigned __int64 *,unsigned __int64 *,ulong)
0x1004a09a5  mov     rax, cs:__imp_VirtualAllocExNuma
0x1004a09ac  mov     cs:?sm_VirtualAllocExNumaLarge@MemoryNode@@0P6APEAXPEAX0_KKKK@ZEA, rax; void * (*MemoryNode::sm_VirtualAllocExNumaLarge)(void *,void *,unsigned __int64,ulong,ulong,ulong)
0x1004a09b3  call    cs:__imp_GetModuleHandleW
0x1004a09b9  mov     rcx, rax; hModule
0x1004a09bc  lea     rdx, aNtallocateuser; "NtAllocateUserPhysicalPagesEx"
0x1004a09c3  call    cs:__imp_GetProcAddress
0x1004a09c9  mov     cs:?sm_NtAllocateUserPhysicalPagesEx@MemoryNode@@0P6AJPEAXPEA_K1PEAUMEM_EXTENDED_PARAMETER@@K@ZEA, rax; long (*MemoryNode::sm_NtAllocateUserPhysicalPagesEx)(void *,unsigned __int64 *,unsigned __int64 *,MEM_EXTENDED_PARAMETER *,ulong)
0x1004a09d0  test    byte ptr cs:?sm_osStatus@SOS_PublicGlobals@@2KA, 10h; ulong SOS_PublicGlobals::sm_osStatus
0x1004a09d7  jnz     short loc_1004A09E5
0x1004a09d9  mov     cs:?MemoryNode_LargePageSize@@3_KA, rsi; unsigned __int64 MemoryNode_LargePageSize
0x1004a09e0  jmp     loc_1004A0AC2
0x1004a09e5  cmp     cs:?MemoryNode_LargePageSize@@3_KA, rsi; unsigned __int64 MemoryNode_LargePageSize
0x1004a09ec  jz      loc_1004A0AC2
0x1004a09f2  cmp     cs:?SOS_OS_MemoryModel@@3W4SOS_MemoryModel@@A, 1; SOS_MemoryModel SOS_OS_MemoryModel
0x1004a09f9  jz      loc_1004A0AC2
0x1004a09ff  movzx   eax, word ptr [rbx+80h]
0x1004a0a06  lea     rdx, ?sm_perNodePreAllocation@LargePageAllocator@@0PAPEAEA; uchar * near * LargePageAllocator::sm_perNodePreAllocation
0x1004a0a0d  mov     rcx, rsi
0x1004a0a10  xchg    rcx, [rdx+rax*8]
0x1004a0a14  test    rcx, rcx
0x1004a0a17  jnz     short loc_1004A0A2D
0x1004a0a19  mov     rcx, rbx; struct MemoryNode *
0x1004a0a1c  call    ?AllocateBuffer@LargePageAllocator@@CAPEAEPEAVMemoryNode@@@Z; LargePageAllocator::AllocateBuffer(MemoryNode *)
0x1004a0a21  mov     rcx, rax
0x1004a0a24  test    rax, rax
0x1004a0a27  jz      loc_1004A0AC2
0x1004a0a2d  mov     r8, cs:?MemoryNode_LargePageSize@@3_KA; unsigned __int64 MemoryNode_LargePageSize
0x1004a0a34  xor     edx, edx
0x1004a0a36  mov     [rbx+0C8h], rcx
0x1004a0a3d  mov     [rbx+0C4h], esi
0x1004a0a43  lea     r9, [r8+1FFFFFFh]
0x1004a0a4a  mov     rax, r9
0x1004a0a4d  div     r8
0x1004a0a50  sub     r9, rdx
0x1004a0a53  lea     rdx, [rbx+0E0h]
0x1004a0a5a  mov     [rdx+8], rdx
0x1004a0a5e  mov     [rdx], rdx
0x1004a0a61  mov     [rbx+0D0h], r9
0x1004a0a68  lea     r8, [r9+rcx]
0x1004a0a6c  cmp     rcx, r8
0x1004a0a6f  jnb     short loc_1004A0AB8
0x1004a0a71  lfence
0x1004a0a74  nop     dword ptr [rax+00h]
0x1004a0a78  nop     dword ptr [rax+rax+00000000h]
0x1004a0a80  mov     [rcx], rsi
0x1004a0a83  mov     [rcx+8], rsi
0x1004a0a87  mov     rax, [rdx]
0x1004a0a8a  mov     [rcx], rax
0x1004a0a8d  mov     rax, [rdx]
0x1004a0a90  mov     [rax+8], rcx
0x1004a0a94  mov     [rdx], rcx
0x1004a0a97  mov     [rcx+8], rdx
0x1004a0a9b  add     rcx, 2000h
0x1004a0aa2  mov     rax, [rbx+0B8h]
0x1004a0aa9  inc     rax
0x1004a0aac  mov     [rbx+0B8h], rax
0x1004a0ab3  cmp     rcx, r8
0x1004a0ab6  jb      short loc_1004A0A80
0x1004a0ab8  mov     dword ptr [rbx+0C0h], 1
0x1004a0ac2  mov     eax, [rbx+30h]
0x1004a0ac5  mov     rsi, [rsp+0F8h+arg_18]
0x1004a0acd  test    eax, eax
0x1004a0acf  jnz     short loc_1004A0B1F
0x1004a0ad1  mov     rax, rdi
0x1004a0ad4  lock xadd [rbx+38h], rax
0x1004a0ada  lock xadd [rbx+40h], rdi
0x1004a0ae0  cmp     cs:dword_100720F58, 1
0x1004a0ae7  jz      short loc_1004A0B1F
0x1004a0ae9  mov     r8, [rbx+0A8h]
0x1004a0af0  mov     rcx, [rbx+90h]
0x1004a0af7  mov     rax, [rbx+50h]
0x1004a0afb  inc     rax
0x1004a0afe  add     rax, [rbx+48h]
0x1004a0b02  cmp     r8, rcx
0x1004a0b05  cmovge  r8, rcx
0x1004a0b09  add     rax, [rbx+40h]
0x1004a0b0d  cqo
0x1004a0b0f  sub     rax, rdx
0x1004a0b12  sar     rax, 1
0x1004a0b15  cmp     r8, rax
0x1004a0b18  jnz     short loc_1004A0B1F
0x1004a0b1a  call    ?RecalculateTarget@MemoryNode@@SAXXZ; MemoryNode::RecalculateTarget(void)
0x1004a0b1f  cmp     cs:byte_100713B81, 0
0x1004a0b26  mov     rdi, [rsp+0F8h+var_8]
0x1004a0b2e  mov     rbx, [rsp+0F8h+arg_8]
0x1004a0b36  jz      short loc_1004A0BA1
0x1004a0b38  xor     edx, edx; hFile
0x1004a0b3a  lea     rcx, aDkdllDll; "dkdll.dll"
0x1004a0b41  mov     r8d, 800h; dwFlags
0x1004a0b47  call    cs:__imp_LoadLibraryExW
0x1004a0b4d  test    rax, rax
0x1004a0b50  jz      short loc_1004A0B7D
0x1004a0b52  lea     rdx, aNtmapviewoffil; "NtMapViewOfFileExNumaProtection"
0x1004a0b59  mov     rcx, rax; hModule
0x1004a0b5c  call    cs:__imp_GetProcAddress
0x1004a0b62  mov     cs:?sm_NtMapViewOfFileExNumaProtection@MemoryNode@@0P6APEAXPEAXKKK_K0KPEAI@ZEA, rax; void * (*MemoryNode::sm_NtMapViewOfFileExNumaProtection)(void *,ulong,ulong,ulong,unsigned __int64,void *,ulong,uint *)
0x1004a0b69  test    rax, rax
0x1004a0b6c  jnz     short loc_1004A0BA1
0x1004a0b6e  call    cs:__imp_GetLastError
0x1004a0b74  lea     rcx, aFailedToRetrie; "Failed to retrieve the address of NtMap"...
0x1004a0b7b  jmp     short loc_1004A0B8A
0x1004a0b7d  call    cs:__imp_GetLastError
0x1004a0b83  lea     rcx, aFailedToLoadDk; "Failed to load dkdll.dll with %d.\n"
0x1004a0b8a  mov     r8, cs:?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x1004a0b91  mov     edx, eax
0x1004a0b93  test    r8, r8
0x1004a0b96  cmovz   r8, cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x1004a0b9e  call    r8
0x1004a0ba1  mov     rcx, [rsp+0F8h+var_28]
0x1004a0ba9  xor     rcx, rsp; StackCookie
0x1004a0bac  call    __security_check_cookie
0x1004a0bb1  add     rsp, 0F8h
0x1004a0bb8  retn
```
