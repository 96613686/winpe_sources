# CSubscriptionMgr::GetSubscriptionRunState(ulong,_GUID const *,ulong *)

- ea: `0x180019570`
- end: `0x180019629`
- name: `?GetSubscriptionRunState@CSubscriptionMgr@@UEAAJKPEBU_GUID@@PEAK@Z`
- size: `185`
- prototype: `int(CSubscriptionMgr *__hidden this, unsigned int, const struct _GUID *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180019570`
- `0x18002924e`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800195be`
- `ole32!CoCreateInstance` at `0x1800195be`

## pseudocode

```c
__int64 __fastcall CSubscriptionMgr::GetSubscriptionRunState(
        CSubscriptionMgr *this,
        unsigned int a2,
        const struct _GUID *a3,
        unsigned int *a4)
{
  __int64 v4; // rbx
  unsigned int v7; // ebx
  LPVOID v9; // [rsp+30h] [rbp-18h] BYREF

  v4 = a2;
  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  v9 = 0;
  if ( CoCreateInstance(&CLSID_SubscriptionThrottler, 0, 5u, &IID_ISubscriptionThrottler, &v9) < 0 )
  {
    if ( (_DWORD)v4 )
      memset_0(a4, 0, 4 * v4);
    return 1;
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const struct _GUID *, unsigned int *))(*(_QWORD *)v9 + 24LL))(
           v9,
           (unsigned int)v4,
           a3,
           a4);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x180019570  mov     r11, rsp
0x180019573  mov     [r11+8], rbx
0x180019577  mov     [r11+10h], rsi
0x18001957b  push    rdi
0x18001957c  sub     rsp, 40h
0x180019580  mov     ebx, edx
0x180019582  mov     rdi, r9
0x180019585  mov     rsi, r8
0x180019588  test    edx, edx
0x18001958a  jz      loc_180019614
0x180019590  test    r8, r8
0x180019593  jz      short loc_180019614
0x180019595  test    r9, r9
0x180019598  jz      short loc_180019614
0x18001959a  xor     edx, edx; pUnkOuter
0x18001959c  mov     qword ptr [r11-18h], 0
0x1800195a4  lea     rax, [r11-18h]
0x1800195a8  lea     r9, IID_ISubscriptionThrottler; riid
0x1800195af  mov     [r11-28h], rax
0x1800195b3  lea     rcx, CLSID_SubscriptionThrottler; rclsid
0x1800195ba  lea     r8d, [rdx+5]; dwClsContext
0x1800195be  call    cs:__imp_CoCreateInstance
0x1800195c4  test    eax, eax
0x1800195c6  js      short loc_1800195F6
0x1800195c8  mov     rcx, [rsp+48h+var_18]
0x1800195cd  mov     r9, rdi
0x1800195d0  mov     r8, rsi
0x1800195d3  mov     edx, ebx
0x1800195d5  mov     rax, [rcx]
0x1800195d8  mov     rax, [rax+18h]
0x1800195dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195e1  mov     rcx, [rsp+48h+var_18]
0x1800195e6  mov     ebx, eax
0x1800195e8  mov     rdx, [rcx]
0x1800195eb  mov     rax, [rdx+10h]
0x1800195ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195f4  jmp     short loc_180019610
0x1800195f6  test    ebx, ebx
0x1800195f8  jz      short loc_18001960B
0x1800195fa  mov     r8, rbx
0x1800195fd  xor     edx, edx; Val
0x1800195ff  shl     r8, 2; Size
0x180019603  mov     rcx, rdi; void *
0x180019606  call    memset_0
0x18001960b  mov     ebx, 1
0x180019610  mov     eax, ebx
0x180019612  jmp     short loc_180019619
0x180019614  mov     eax, 80070057h
0x180019619  mov     rbx, [rsp+48h+arg_0]
0x18001961e  mov     rsi, [rsp+48h+arg_8]
0x180019623  add     rsp, 40h
0x180019627  pop     rdi
0x180019628  retn
```
