# ContextFree

- ea: `0x18001a4b4`
- end: `0x18001a6b9`
- name: `ContextFree`
- size: `517`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180011b28`
- `0x18001e4b0`
- `0x1800206d0`

## callees

- `0x180006d00`
- `0x180006de0`
- `0x180009770`
- `0x1800185b8`
- `0x180018b18`
- `0x1800192a8`
- `0x18001a4b4`
- `0x18002ab18`
- `0x180038010`

## import_xrefs

- `ntdll!NtClose` at `0x18001a5ba`
- `ntdll!NtClose` at `0x18001a5ba`
- `ntdll!RtlEnterCriticalSection` at `0x18001a511`
- `ntdll!RtlEnterCriticalSection` at `0x18001a511`
- `ntdll!RtlDeleteCriticalSection` at `0x18001a676`
- `ntdll!RtlDeleteCriticalSection` at `0x18001a676`

## pseudocode

```c
__int64 __fastcall ContextFree(char *hMem)
{
  PVOID *v3; // rcx
  __int64 i; // rdi
  void *v5; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids, hMem);
  if ( !hMem )
    return 3221225485LL;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(hMem + 648));
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        &WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids,
        *((unsigned int *)hMem + 4));
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 4) != 0 )
    {
      WPP_SF_dd(
        v3[2],
        21,
        &WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids,
        *((unsigned int *)hMem + 139),
        *((_DWORD *)hMem + 138));
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( *((_QWORD *)hMem + 68) )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 4) != 0 )
      WPP_SF_dd(
        v3[2],
        22,
        &WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids,
        *((unsigned int *)hMem + 139),
        *((_DWORD *)hMem + 138));
    NtClose(*((HANDLE *)hMem + 68));
    *((_QWORD *)hMem + 68) = 0;
  }
  StringFree(hMem + 64);
  StringFree(hMem + 80);
  StringFree(hMem + 112);
  StringFree(hMem + 128);
  UnicodeStringFree(hMem + 568);
  UnicodeStringFree(hMem + 584);
  UnicodeStringFree(hMem + 600);
  StringFree(hMem + 144);
  for ( i = 0; i != 24; ++i )
    StringFree(&hMem[16 * i + 160]);
  if ( *((_QWORD *)hMem + 79) )
    (**(void (***)(void))(*((_QWORD *)hMem + 78) + 24LL))();
  v5 = (void *)*((_QWORD *)hMem + 78);
  if ( v5 )
    SsiIStoreRelease(v5);
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(hMem + 648));
  DigestFreeMemory(hMem);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids, hMem);
  return 0;
}

```

## disassembly

```asm
0x18001a4b4  push    rbx
0x18001a4b6  push    rbp
0x18001a4b7  push    rsi
0x18001a4b8  push    rdi
0x18001a4b9  push    r14
0x18001a4bb  push    r15
0x18001a4bd  sub     rsp, 38h
0x18001a4c1  mov     rbx, rcx
0x18001a4c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4cb  lea     r14, WPP_GLOBAL_Control
0x18001a4d2  lea     r15, WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids
0x18001a4d9  cmp     rcx, r14
0x18001a4dc  jz      short loc_18001A4F8
0x18001a4de  test    byte ptr [rcx+1Ch], 80h
0x18001a4e2  jz      short loc_18001A4F8
0x18001a4e4  mov     rcx, [rcx+10h]
0x18001a4e8  mov     edx, 13h
0x18001a4ed  mov     r9, rbx
0x18001a4f0  mov     r8, r15
0x18001a4f3  call    WPP_SF_q
0x18001a4f8  test    rbx, rbx
0x18001a4fb  jnz     short loc_18001A507
0x18001a4fd  mov     eax, 0C000000Dh
0x18001a502  jmp     loc_18001A6AC
0x18001a507  lea     rbp, [rbx+288h]
0x18001a50e  mov     rcx, rbp; CriticalSection
0x18001a511  call    cs:__imp_RtlEnterCriticalSection
0x18001a517  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a51e  mov     dil, 4
0x18001a521  cmp     rcx, r14
0x18001a524  jz      short loc_18001A57C
0x18001a526  test    [rcx+1Ch], dil
0x18001a52a  jz      short loc_18001A548
0x18001a52c  mov     rcx, [rcx+10h]
0x18001a530  mov     edx, 14h
0x18001a535  mov     r9d, [rbx+10h]
0x18001a539  mov     r8, r15
0x18001a53c  call    WPP_SF_d
0x18001a541  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a548  cmp     rcx, r14
0x18001a54b  jz      short loc_18001A57C
0x18001a54d  test    [rcx+1Ch], dil
0x18001a551  jz      short loc_18001A57C
0x18001a553  mov     eax, [rbx+228h]
0x18001a559  mov     edx, 15h
0x18001a55e  mov     r9d, [rbx+22Ch]
0x18001a565  mov     r8, r15
0x18001a568  mov     rcx, [rcx+10h]
0x18001a56c  mov     [rsp+68h+var_48], eax
0x18001a570  call    WPP_SF_dd
0x18001a575  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a57c  cmp     qword ptr [rbx+220h], 0
0x18001a584  jz      short loc_18001A5CB
0x18001a586  cmp     rcx, r14
0x18001a589  jz      short loc_18001A5B3
0x18001a58b  test    [rcx+1Ch], dil
0x18001a58f  jz      short loc_18001A5B3
0x18001a591  mov     eax, [rbx+228h]
0x18001a597  mov     edx, 16h
0x18001a59c  mov     r9d, [rbx+22Ch]
0x18001a5a3  mov     r8, r15
0x18001a5a6  mov     rcx, [rcx+10h]
0x18001a5aa  mov     [rsp+68h+var_48], eax
0x18001a5ae  call    WPP_SF_dd
0x18001a5b3  mov     rcx, [rbx+220h]; Handle
0x18001a5ba  call    cs:__imp_NtClose
0x18001a5c0  mov     qword ptr [rbx+220h], 0
0x18001a5cb  lea     rcx, [rbx+40h]
0x18001a5cf  call    StringFree
0x18001a5d4  lea     rcx, [rbx+50h]
0x18001a5d8  call    StringFree
0x18001a5dd  lea     rcx, [rbx+70h]
0x18001a5e1  call    StringFree
0x18001a5e6  lea     rcx, [rbx+80h]
0x18001a5ed  call    StringFree
0x18001a5f2  lea     rcx, [rbx+238h]
0x18001a5f9  call    UnicodeStringFree
0x18001a5fe  lea     rcx, [rbx+248h]
0x18001a605  call    UnicodeStringFree
0x18001a60a  lea     rcx, [rbx+258h]
0x18001a611  call    UnicodeStringFree
0x18001a616  lea     rcx, [rbx+90h]
0x18001a61d  call    StringFree
0x18001a622  xor     edi, edi
0x18001a624  lea     rsi, [rbx+0A0h]
0x18001a62b  mov     rcx, rdi
0x18001a62e  shl     rcx, 4
0x18001a632  add     rcx, rsi
0x18001a635  call    StringFree
0x18001a63a  inc     rdi
0x18001a63d  cmp     rdi, 18h
0x18001a641  jnz     short loc_18001A62B
0x18001a643  mov     rcx, [rbx+278h]
0x18001a64a  test    rcx, rcx
0x18001a64d  jz      short loc_18001A662
0x18001a64f  mov     rax, [rbx+270h]
0x18001a656  mov     rdx, [rax+18h]
0x18001a65a  mov     rax, [rdx]
0x18001a65d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a662  mov     rcx, [rbx+270h]; hMem
0x18001a669  test    rcx, rcx
0x18001a66c  jz      short loc_18001A673
0x18001a66e  call    SsiIStoreRelease
0x18001a673  mov     rcx, rbp; CriticalSection
0x18001a676  call    cs:__imp_RtlDeleteCriticalSection
0x18001a67c  mov     rcx, rbx; hMem
0x18001a67f  call    DigestFreeMemory
0x18001a684  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a68b  cmp     rcx, r14
0x18001a68e  jz      short loc_18001A6AA
0x18001a690  test    byte ptr [rcx+1Ch], 80h
0x18001a694  jz      short loc_18001A6AA
0x18001a696  mov     rcx, [rcx+10h]
0x18001a69a  mov     edx, 17h
0x18001a69f  mov     r9, rbx
0x18001a6a2  mov     r8, r15
0x18001a6a5  call    WPP_SF_q
0x18001a6aa  xor     eax, eax
0x18001a6ac  add     rsp, 38h
0x18001a6b0  pop     r15
0x18001a6b2  pop     r14
0x18001a6b4  pop     rdi
0x18001a6b5  pop     rsi
0x18001a6b6  pop     rbp
0x18001a6b7  pop     rbx
0x18001a6b8  retn
```
