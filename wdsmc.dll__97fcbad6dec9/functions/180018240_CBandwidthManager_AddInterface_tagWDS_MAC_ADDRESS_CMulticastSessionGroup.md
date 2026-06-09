# CBandwidthManager::AddInterface(tagWDS_MAC_ADDRESS *,CMulticastSessionGroup *)

- ea: `0x180018240`
- end: `0x18001847f`
- name: `?AddInterface@CBandwidthManager@@AEAAKPEAUtagWDS_MAC_ADDRESS@@PEAVCMulticastSessionGroup@@@Z`
- size: `575`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct tagWDS_MAC_ADDRESS *Buf2, struct CMulticastSessionGroup *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018770`

## callees

- `0x180018240`
- `0x180018488`
- `0x1800186a0`
- `0x18001a9a8`
- `0x180023c50`
- `0x180023e54`
- `0x180024228`
- `0x180025850`
- `0x180026670`
- `0x1800266a0`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001842b`
- `KERNEL32!LeaveCriticalSection` at `0x180018450`
- `KERNEL32!LeaveCriticalSection` at `0x18001842b`
- `KERNEL32!LeaveCriticalSection` at `0x180018450`
- `KERNEL32!EnterCriticalSection` at `0x180018274`
- `KERNEL32!EnterCriticalSection` at `0x1800183d6`
- `KERNEL32!EnterCriticalSection` at `0x180018274`
- `KERNEL32!EnterCriticalSection` at `0x1800183d6`
- `KERNEL32!InitializeCriticalSection` at `0x180018306`
- `KERNEL32!InitializeCriticalSection` at `0x180018306`

## string_xrefs

- `0x180018289`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x1800182bc`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall CBandwidthManager::AddInterface(
        char *lpCriticalSection,
        struct tagWDS_MAC_ADDRESS *Buf2,
        struct CMulticastSessionGroup *a3)
{
  unsigned int InterfaceAttributes2; // eax
  const char *v7; // rdx
  unsigned int v8; // eax
  const char *v9; // rdx
  unsigned int InterfaceAttributes1; // esi
  const char *v11; // rdx
  unsigned int v12; // eax
  struct tagWDS_INTERFACE_ATTRIBUTES *v13; // r14
  char *v14; // rax
  _QWORD *v15; // rbx
  void (*v16)(const unsigned __int16 *, ...); // rsi
  unsigned int v17; // eax
  __int64 v18; // r8
  unsigned __int16 *v19; // rdx
  const char *v20; // rdx
  struct tagWDS_INTERFACE_ATTRIBUTES *v22[2]; // [rsp+20h] [rbp-D8h] BYREF
  BOOL v23; // [rsp+30h] [rbp-C8h]
  unsigned __int16 v24[70]; // [rsp+34h] [rbp-C4h] BYREF

  v22[0] = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  InterfaceAttributes2 = GetInterfaceAttributes2(Buf2, v22);
  v8 = ElValidateWin32(InterfaceAttributes2, v7, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0xBB2u);
  InterfaceAttributes1 = v8;
  if ( v8 == 120 || v8 == 2 )
    InterfaceAttributes1 = GetInterfaceAttributes1(Buf2, v22);
  ElValidateWin32(InterfaceAttributes1, v9, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0xBBDu);
  v12 = ElValidateWin32(InterfaceAttributes1, v11, "base\\eco\\wds\\transport\\server\\mc\\bandwidthmanager.cpp", 0x99u);
  v13 = v22[0];
  if ( !v12 )
  {
    v14 = (char *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
    v15 = v14;
    if ( v14 )
    {
      InitializeCriticalSection((LPCRITICAL_SECTION)(v14 + 56));
      v15[4] = 0;
      v15[5] = 0;
      *((_DWORD *)v15 + 12) = 0;
      v15[12] = 0;
      v15[13] = 0;
    }
    else
    {
      v15 = 0;
    }
    if ( v15 )
    {
      memmove_0(v15, Buf2, 0x14u);
      v16 = g_ErrLibTraceFunction;
      v15[3] = *(_QWORD *)v13 >> 3;
      if ( v16 )
      {
        v17 = HexToString((const unsigned __int8 *)Buf2, *((unsigned int *)Buf2 + 4), v24, 0x40u);
        v18 = v15[3];
        v19 = v24;
        v23 = v17 != 0;
        if ( v17 )
          v19 = L"<<Failed>>";
        v16(L"[Bandwidth] NIC=%s, Bandwidth=%I64uBps", v19, v18);
      }
      InterfaceAttributes1 = CBandwidthManager::AddMulticastSessionGroup(
                               (LPCRITICAL_SECTION)lpCriticalSection,
                               (struct CBandwidthManager::Interface *)v15,
                               a3);
      if ( !ElValidateWin32(
              InterfaceAttributes1,
              v20,
              "base\\eco\\wds\\transport\\server\\mc\\bandwidthmanager.cpp",
              0xB2u) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 216));
        if ( *((_QWORD *)lpCriticalSection + 25) )
        {
          v15[12] = 0;
          v15[13] = *((_QWORD *)lpCriticalSection + 26);
          *(_QWORD *)(*((_QWORD *)lpCriticalSection + 26) + 96LL) = v15;
          *((_QWORD *)lpCriticalSection + 26) = v15;
        }
        else
        {
          *((_QWORD *)lpCriticalSection + 26) = v15;
          *((_QWORD *)lpCriticalSection + 25) = v15;
          v15[12] = 0;
          v15[13] = 0;
        }
        ++*((_DWORD *)lpCriticalSection + 64);
        LeaveCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 216));
        v15 = 0;
      }
      if ( v15 )
        CBandwidthManager::Interface::`scalar deleting destructor'((CBandwidthManager::Interface *)v15);
    }
    else
    {
      InterfaceAttributes1 = 8;
    }
  }
  if ( v13 )
    operator delete(v13);
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  return InterfaceAttributes1;
}

```

## disassembly

```asm
0x180018240  mov     [rsp+arg_18], rbx
0x180018245  push    rbp
0x180018246  push    rsi
0x180018247  push    rdi
0x180018248  push    r14
0x18001824a  push    r15
0x18001824c  sub     rsp, 0D0h
0x180018253  mov     rax, cs:__security_cookie
0x18001825a  xor     rax, rsp
0x18001825d  mov     [rsp+0F8h+var_38], rax
0x180018265  and     [rsp+0F8h+var_D8], 0
0x18001826b  mov     r15, r8
0x18001826e  mov     rbp, rdx
0x180018271  mov     rdi, rcx
0x180018274  call    cs:__imp_EnterCriticalSection
0x18001827a  lea     rdx, [rsp+0F8h+var_D8]; struct tagWDS_INTERFACE_ATTRIBUTES **
0x18001827f  mov     rcx, rbp; Buf2
0x180018282  call    ?GetInterfaceAttributes2@@YAKPEAUtagWDS_MAC_ADDRESS@@PEAPEAUtagWDS_INTERFACE_ATTRIBUTES@@@Z; GetInterfaceAttributes2(tagWDS_MAC_ADDRESS *,tagWDS_INTERFACE_ATTRIBUTES * *)
0x180018287  mov     ecx, eax; unsigned int
0x180018289  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180018290  mov     r9d, 0BB2h; unsigned int
0x180018296  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001829b  mov     esi, eax
0x18001829d  cmp     eax, 78h ; 'x'
0x1800182a0  jz      short loc_1800182A7
0x1800182a2  cmp     eax, 2
0x1800182a5  jnz     short loc_1800182B6
0x1800182a7  lea     rdx, [rsp+0F8h+var_D8]; struct tagWDS_INTERFACE_ATTRIBUTES **
0x1800182ac  mov     rcx, rbp; Buf2
0x1800182af  call    ?GetInterfaceAttributes1@@YAKPEAUtagWDS_MAC_ADDRESS@@PEAPEAUtagWDS_INTERFACE_ATTRIBUTES@@@Z; GetInterfaceAttributes1(tagWDS_MAC_ADDRESS *,tagWDS_INTERFACE_ATTRIBUTES * *)
0x1800182b4  mov     esi, eax
0x1800182b6  mov     r9d, 0BBDh; unsigned int
0x1800182bc  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800182c3  mov     ecx, esi; unsigned int
0x1800182c5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800182ca  mov     r9d, 99h; unsigned int
0x1800182d0  lea     r8, aBaseEcoWdsTran_20; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800182d7  mov     ecx, esi; unsigned int
0x1800182d9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800182de  mov     r14, [rsp+0F8h+var_D8]
0x1800182e3  test    eax, eax
0x1800182e5  jnz     loc_180018440
0x1800182eb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800182f2  lea     ecx, [rax+70h]; unsigned __int64
0x1800182f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800182fa  mov     rbx, rax
0x1800182fd  test    rax, rax
0x180018300  jz      short loc_180018326
0x180018302  lea     rcx, [rax+38h]; lpCriticalSection
0x180018306  call    cs:__imp_InitializeCriticalSection
0x18001830c  and     qword ptr [rbx+20h], 0
0x180018311  and     qword ptr [rbx+28h], 0
0x180018316  and     dword ptr [rbx+30h], 0
0x18001831a  and     qword ptr [rbx+60h], 0
0x18001831f  and     qword ptr [rbx+68h], 0
0x180018324  jmp     short loc_180018328
0x180018326  xor     ebx, ebx
0x180018328  test    rbx, rbx
0x18001832b  jnz     short loc_180018335
0x18001832d  lea     esi, [rbx+8]
0x180018330  jmp     loc_180018440
0x180018335  mov     r8d, 14h; Size
0x18001833b  mov     rdx, rbp; Src
0x18001833e  mov     rcx, rbx; void *
0x180018341  call    memmove_0
0x180018346  mov     rax, [r14]
0x180018349  mov     rsi, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180018350  shr     rax, 3
0x180018354  mov     [rbx+18h], rax
0x180018358  test    rsi, rsi
0x18001835b  jz      short loc_1800183A4
0x18001835d  mov     edx, [rbp+10h]; unsigned __int64
0x180018360  lea     r8, [rsp+0F8h+var_C4]; unsigned __int16 *
0x180018365  mov     r9d, 40h ; '@'; unsigned __int64
0x18001836b  mov     rcx, rbp; unsigned __int8 *
0x18001836e  call    ?HexToString@@YAKPEBE_KPEAG1@Z; HexToString(uchar const *,unsigned __int64,ushort *,unsigned __int64)
0x180018373  mov     r8, [rbx+18h]
0x180018377  lea     rdx, [rsp+0F8h+var_C4]
0x18001837c  xor     ecx, ecx
0x18001837e  test    eax, eax
0x180018380  setnz   cl
0x180018383  test    eax, eax
0x180018385  mov     [rsp+0F8h+var_C8], ecx
0x180018389  mov     rax, rsi
0x18001838c  lea     rcx, aFailed; "<<Failed>>"
0x180018393  cmovnz  rdx, rcx
0x180018397  lea     rcx, aBandwidthNicSB; "[Bandwidth] NIC=%s, Bandwidth=%I64uBps"
0x18001839e  call    cs:__guard_dispatch_icall_fptr
0x1800183a4  mov     r8, r15; struct CMulticastSessionGroup *
0x1800183a7  mov     rdx, rbx; struct CBandwidthManager::Interface *
0x1800183aa  mov     rcx, rdi; lpCriticalSection
0x1800183ad  call    ?AddMulticastSessionGroup@CBandwidthManager@@AEAAKPEAUInterface@1@PEAVCMulticastSessionGroup@@@Z; CBandwidthManager::AddMulticastSessionGroup(CBandwidthManager::Interface *,CMulticastSessionGroup *)
0x1800183b2  mov     r9d, 0B2h; unsigned int
0x1800183b8  lea     r8, aBaseEcoWdsTran_20; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800183bf  mov     ecx, eax; unsigned int
0x1800183c1  mov     esi, eax
0x1800183c3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800183c8  test    eax, eax
0x1800183ca  jnz     short loc_180018433
0x1800183cc  lea     rbp, [rdi+0D8h]
0x1800183d3  mov     rcx, rbp; lpCriticalSection
0x1800183d6  call    cs:__imp_EnterCriticalSection
0x1800183dc  cmp     qword ptr [rdi+0C8h], 0
0x1800183e4  jnz     short loc_180018400
0x1800183e6  mov     [rdi+0D0h], rbx
0x1800183ed  mov     [rdi+0C8h], rbx
0x1800183f4  and     qword ptr [rbx+60h], 0
0x1800183f9  and     qword ptr [rbx+68h], 0
0x1800183fe  jmp     short loc_180018422
0x180018400  and     qword ptr [rbx+60h], 0
0x180018405  mov     rax, [rdi+0D0h]
0x18001840c  mov     [rbx+68h], rax
0x180018410  mov     rax, [rdi+0D0h]
0x180018417  mov     [rax+60h], rbx
0x18001841b  mov     [rdi+0D0h], rbx
0x180018422  inc     dword ptr [rdi+100h]
0x180018428  mov     rcx, rbp; lpCriticalSection
0x18001842b  call    cs:__imp_LeaveCriticalSection
0x180018431  xor     ebx, ebx
0x180018433  test    rbx, rbx
0x180018436  jz      short loc_180018440
0x180018438  mov     rcx, rbx; this
0x18001843b  call    ??_GInterface@CBandwidthManager@@QEAAPEAXI@Z; CBandwidthManager::Interface::`scalar deleting destructor'(uint)
0x180018440  test    r14, r14
0x180018443  jz      short loc_18001844D
0x180018445  mov     rcx, r14; void *
0x180018448  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001844d  mov     rcx, rdi; lpCriticalSection
0x180018450  call    cs:__imp_LeaveCriticalSection
0x180018456  mov     eax, esi
0x180018458  mov     rcx, [rsp+0F8h+var_38]
0x180018460  xor     rcx, rsp; StackCookie
0x180018463  call    __security_check_cookie
0x180018468  mov     rbx, [rsp+0F8h+arg_18]
0x180018470  add     rsp, 0D0h
0x180018477  pop     r15
0x180018479  pop     r14
0x18001847b  pop     rdi
0x18001847c  pop     rsi
0x18001847d  pop     rbp
0x18001847e  retn
```
