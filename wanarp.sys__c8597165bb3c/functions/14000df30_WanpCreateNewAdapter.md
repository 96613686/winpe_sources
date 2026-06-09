# WanpCreateNewAdapter

- ea: `0x14000df30`
- end: `0x14000e270`
- name: `WanpCreateNewAdapter`
- size: `832`
- prototype: `__int64 __fastcall(__int64, __int64, char, char, int, _QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000fdc4`
- `0x140011618`

## callees

- `0x140003060`
- `0x1400050b0`
- `0x1400054c0`
- `0x14000d090`
- `0x14000d1c0`
- `0x14000d620`
- `0x14000df30`
- `0x1400112f0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dfa6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dfa6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e1c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e1c1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dfe1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dfe1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000dfce`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000dfce`
- `ntoskrnl!KeLowerIrql` at `0x14000e040`
- `ntoskrnl!KeLowerIrql` at `0x14000e07c`
- `ntoskrnl!KeLowerIrql` at `0x14000e040`
- `ntoskrnl!KeLowerIrql` at `0x14000e07c`
- `ntoskrnl!ExAllocatePool2` at `0x14000e1a8`
- `ntoskrnl!ExAllocatePool2` at `0x14000e1a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e02f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e06b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e02f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e06b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e1ea`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e1ea`

## pseudocode

```c
__int64 __fastcall WanpCreateNewAdapter(__int64 a1, __int64 a2, char a3, char a4, int a5, _QWORD *a6)
{
  volatile signed __int32 *v7; // r12
  __int64 v9; // rbx
  KIRQL v11; // di
  __int64 DialInAdapterGivenCompartmentId; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 result; // rax
  char AdapterFromDeviceGuid; // al
  __int64 v17; // rcx
  _QWORD *v18; // rdi
  unsigned int v19; // r8d
  unsigned int v20; // r14d
  __int64 v21; // rdi
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 Pool2; // rax
  __int64 v25; // rbx
  PVOID P; // [rsp+30h] [rbp-99h] BYREF
  __int128 v27; // [rsp+38h] [rbp-91h] BYREF
  __int64 v28; // [rsp+48h] [rbp-81h]
  __int64 v29; // [rsp+50h] [rbp-79h]
  __int64 v30; // [rsp+60h] [rbp-69h] BYREF
  int v31; // [rsp+68h] [rbp-61h]
  wchar_t v32; // [rsp+6Ch] [rbp-5Dh]
  __int16 v33; // [rsp+6Eh] [rbp-5Bh]
  _BYTE v34[80]; // [rsp+70h] [rbp-59h] BYREF

  v28 = a1;
  v29 = a2;
  P = 0;
  v7 = &g_ModuleV4;
  if ( !a3 )
    v7 = &g_ModuleV6;
  v9 = -1;
  v27 = 0;
  if ( a5 != 1 )
  {
LABEL_16:
    AdapterFromDeviceGuid = GetAdapterFromDeviceGuid(a1, &P);
    v18 = P;
    v19 = 0;
    if ( AdapterFromDeviceGuid )
    {
      LOBYTE(v17) = a3;
      if ( (unsigned __int8)IsBindingPresent(v17, P) )
        return 3221225485LL;
    }
    v20 = v19;
    if ( !v18 )
    {
      memset(v34, 0, sizeof(v34));
      v31 = *(_DWORD *)L"ICE";
      v32 = aDevice[6];
      v21 = v28;
      v30 = *(_QWORD *)L"\\DEVICE";
      v33 = 92;
      ConvertGuidToString(v28, v34, 40);
      do
        ++v9;
      while ( *((_WORD *)&v30 + v9) );
      *((_QWORD *)&v27 + 1) = &v30;
      LOBYTE(v22) = a3;
      LOWORD(v27) = 2 * v9;
      WORD1(v27) = 2 * v9;
      v20 = WanpCreateAdapter(v21, &v27, v29, v22, a4, &P);
      if ( v20 )
        return v20;
      v18 = P;
    }
    _InterlockedIncrement(v7);
    if ( a4 != 1 )
      goto LABEL_36;
    if ( a3 )
      v23 = v18[21];
    else
      v23 = v18[22];
    if ( !v23 )
    {
      Pool2 = ExAllocatePool2(64, 552, 1768976983);
      v25 = Pool2;
      if ( !Pool2 )
      {
        ExFreePoolWithTag(v18, 0);
        result = 3221225626LL;
        *a6 = 0;
        return result;
      }
      *(_BYTE *)(Pool2 + 20) = a3;
      *(_DWORD *)(Pool2 + 16) = 1953392983;
      *(_BYTE *)(Pool2 + 48) = 0;
      KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 56));
      *(_DWORD *)(v25 + 32) = -1;
      *(_DWORD *)(v25 + 64) = 1;
      *(_DWORD *)(v25 + 140) = 1;
      *(_DWORD *)(v25 + 144) = 4;
      *(_DWORD *)(v25 + 108) = 0;
      *(_QWORD *)(v25 + 96) = 0;
      *(_OWORD *)(v25 + 68) = ServerInterfaceGuid;
      if ( a3 )
        v18[21] = v25;
      else
        v18[22] = v25;
      ++*((_DWORD *)v18 + 46);
    }
    if ( !v20 )
LABEL_36:
      *a6 = v18;
    return v20;
  }
  v11 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
  if ( _InterlockedIncrement(&dword_140009CB0) == 1 )
    KeAcquireSpinLockAtDpcLevel(&SpinLock);
  KeReleaseSpinLockFromDpcLevel(&g_rwlAdapterLock);
  DialInAdapterGivenCompartmentId = WanpFindDialInAdapterGivenCompartmentId(1);
  if ( !a4
    || !DialInAdapterGivenCompartmentId
    || (LOBYTE(v13) = a3, !(unsigned __int8)IsBindingPresent(v13, DialInAdapterGivenCompartmentId)) )
  {
    if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
      KeReleaseSpinLock(&SpinLock, v11);
    else
      KeLowerIrql(v11);
    goto LABEL_16;
  }
  *a6 = v14;
  if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
    KeReleaseSpinLock(&SpinLock, v11);
  else
    KeLowerIrql(v11);
  return 0;
}

```

## disassembly

```asm
0x14000df30  push    rbp
0x14000df32  push    rbx
0x14000df33  push    rsi
0x14000df34  push    rdi
0x14000df35  push    r12
0x14000df37  push    r13
0x14000df39  push    r14
0x14000df3b  push    r15
0x14000df3d  lea     rbp, [rsp-0Fh]
0x14000df42  sub     rsp, 0D8h
0x14000df49  mov     rax, cs:__security_cookie
0x14000df50  xor     rax, rsp
0x14000df53  mov     [rbp+47h+var_50], rax
0x14000df57  mov     r15, [rbp+47h+arg_28]
0x14000df5b  lea     rax, g_ModuleV6
0x14000df62  mov     r14, rcx
0x14000df65  mov     [rsp+110h+var_C8], rcx
0x14000df6a  xor     ecx, ecx
0x14000df6c  mov     [rbp+47h+var_C0], rdx
0x14000df70  test    r8b, r8b
0x14000df73  mov     [rsp+110h+P], rcx
0x14000df78  lea     r12, g_ModuleV4
0x14000df7f  xorps   xmm0, xmm0
0x14000df82  cmovz   r12, rax
0x14000df86  mov     r13b, r9b
0x14000df89  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000df8d  mov     sil, r8b
0x14000df90  cmp     [rbp+47h+arg_20], 1
0x14000df94  movups  [rsp+110h+var_D8], xmm0
0x14000df99  jnz     loc_14000E088
0x14000df9f  lea     rcx, g_rwlAdapterLock; SpinLock
0x14000dfa6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000dfad  nop     dword ptr [rax+rax+00h]
0x14000dfb2  mov     dil, al
0x14000dfb5  lea     edx, [rbx+2]
0x14000dfb8  lock xadd cs:dword_140009CB0, edx
0x14000dfc0  inc     edx
0x14000dfc2  cmp     edx, 1
0x14000dfc5  jnz     short loc_14000DFDA
0x14000dfc7  lea     rcx, SpinLock; SpinLock
0x14000dfce  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000dfd5  nop     dword ptr [rax+rax+00h]
0x14000dfda  lea     rcx, g_rwlAdapterLock; SpinLock
0x14000dfe1  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000dfe8  nop     dword ptr [rax+rax+00h]
0x14000dfed  mov     ecx, 1
0x14000dff2  call    WanpFindDialInAdapterGivenCompartmentId
0x14000dff7  mov     rdx, rax
0x14000dffa  test    r13b, r13b
0x14000dffd  jz      short loc_14000E053
0x14000dfff  test    rax, rax
0x14000e002  jz      short loc_14000E053
0x14000e004  mov     cl, sil
0x14000e007  call    IsBindingPresent
0x14000e00c  test    al, al
0x14000e00e  jz      short loc_14000E053
0x14000e010  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000e014  mov     [r15], rdx
0x14000e017  mov     eax, ebx
0x14000e019  lock xadd cs:dword_140009CB0, eax
0x14000e021  add     eax, ebx
0x14000e023  jnz     short loc_14000E03D
0x14000e025  mov     dl, dil; NewIrql
0x14000e028  lea     rcx, SpinLock; SpinLock
0x14000e02f  call    cs:__imp_KeReleaseSpinLock
0x14000e036  nop     dword ptr [rax+rax+00h]
0x14000e03b  jmp     short loc_14000E04C
0x14000e03d  mov     cl, dil; NewIrql
0x14000e040  call    cs:__imp_KeLowerIrql
0x14000e047  nop     dword ptr [rax+rax+00h]
0x14000e04c  xor     eax, eax
0x14000e04e  jmp     loc_14000E24F
0x14000e053  mov     eax, ebx
0x14000e055  lock xadd cs:dword_140009CB0, eax
0x14000e05d  add     eax, ebx
0x14000e05f  jnz     short loc_14000E079
0x14000e061  mov     dl, dil; NewIrql
0x14000e064  lea     rcx, SpinLock; SpinLock
0x14000e06b  call    cs:__imp_KeReleaseSpinLock
0x14000e072  nop     dword ptr [rax+rax+00h]
0x14000e077  jmp     short loc_14000E088
0x14000e079  mov     cl, dil; NewIrql
0x14000e07c  call    cs:__imp_KeLowerIrql
0x14000e083  nop     dword ptr [rax+rax+00h]
0x14000e088  lea     rdx, [rsp+110h+P]
0x14000e08d  mov     rcx, r14
0x14000e090  call    GetAdapterFromDeviceGuid
0x14000e095  mov     rdi, [rsp+110h+P]
0x14000e09a  xor     r8d, r8d
0x14000e09d  test    al, al
0x14000e09f  jz      short loc_14000E0BA
0x14000e0a1  mov     rdx, rdi
0x14000e0a4  mov     cl, sil
0x14000e0a7  call    IsBindingPresent
0x14000e0ac  test    al, al
0x14000e0ae  jz      short loc_14000E0BA
0x14000e0b0  mov     eax, 0C000000Dh
0x14000e0b5  jmp     loc_14000E24F
0x14000e0ba  mov     r14d, r8d
0x14000e0bd  test    rdi, rdi
0x14000e0c0  jnz     loc_14000E16A
0x14000e0c6  xor     edx, edx; Val
0x14000e0c8  lea     r8d, [rdi+50h]; Size
0x14000e0cc  lea     rcx, [rbp+47h+var_A0]; void *
0x14000e0d0  call    memset
0x14000e0d5  mov     eax, dword ptr cs:aDevice+8; "ICE"
0x14000e0db  lea     r8d, [rdi+28h]
0x14000e0df  movsd   xmm0, qword ptr cs:aDevice; "\\DEVICE"
0x14000e0e7  lea     rdx, [rbp+47h+var_A0]
0x14000e0eb  mov     [rbp+47h+var_A8], eax
0x14000e0ee  movzx   eax, word ptr cs:aDevice+0Ch; "E"
0x14000e0f5  mov     [rbp+47h+var_A4], ax
0x14000e0f9  lea     eax, [rdi+5Ch]
0x14000e0fc  mov     rdi, [rsp+110h+var_C8]
0x14000e101  mov     rcx, rdi
0x14000e104  movsd   [rbp+47h+var_B0], xmm0
0x14000e109  mov     [rbp+47h+var_A2], ax
0x14000e10d  call    ConvertGuidToString
0x14000e112  lea     rcx, [rbp+47h+var_B0]
0x14000e116  xor     eax, eax
0x14000e118  inc     rbx
0x14000e11b  cmp     [rcx+rbx*2], ax
0x14000e11f  jnz     short loc_14000E118
0x14000e121  mov     r8, [rbp+47h+var_C0]
0x14000e125  lea     rax, [rbp+47h+var_B0]
0x14000e129  mov     qword ptr [rsp+110h+var_D8+8], rax
0x14000e12e  lea     rdx, [rsp+110h+var_D8]
0x14000e133  lea     rax, [rsp+110h+P]
0x14000e138  add     bx, bx
0x14000e13b  mov     [rsp+110h+var_E8], rax
0x14000e140  mov     r9b, sil
0x14000e143  mov     rcx, rdi
0x14000e146  mov     [rsp+110h+var_F0], r13b
0x14000e14b  mov     word ptr [rsp+110h+var_D8], bx
0x14000e150  mov     word ptr [rsp+110h+var_D8+2], bx
0x14000e155  call    WanpCreateAdapter
0x14000e15a  mov     r14d, eax
0x14000e15d  test    eax, eax
0x14000e15f  jnz     loc_14000E24C
0x14000e165  mov     rdi, [rsp+110h+P]
0x14000e16a  lock inc dword ptr [r12]
0x14000e16f  cmp     r13b, 1
0x14000e173  jnz     loc_14000E249
0x14000e179  xor     r12d, r12d
0x14000e17c  test    sil, sil
0x14000e17f  jz      short loc_14000E18A
0x14000e181  mov     rax, [rdi+0A8h]
0x14000e188  jmp     short loc_14000E191
0x14000e18a  mov     rax, [rdi+0B0h]
0x14000e191  test    rax, rax
0x14000e194  jnz     loc_14000E244
0x14000e19a  mov     edx, 228h
0x14000e19f  lea     ecx, [rax+40h]
0x14000e1a2  mov     r8d, 69707257h
0x14000e1a8  call    cs:__imp_ExAllocatePool2
0x14000e1af  nop     dword ptr [rax+rax+00h]
0x14000e1b4  mov     rbx, rax
0x14000e1b7  test    rax, rax
0x14000e1ba  jnz     short loc_14000E1D7
0x14000e1bc  xor     edx, edx; Tag
0x14000e1be  mov     rcx, rdi; P
0x14000e1c1  call    cs:__imp_ExFreePoolWithTag
0x14000e1c8  nop     dword ptr [rax+rax+00h]
0x14000e1cd  mov     eax, 0C000009Ah
0x14000e1d2  mov     [r15], r12
0x14000e1d5  jmp     short loc_14000E24F
0x14000e1d7  lea     rcx, [rax+38h]; SpinLock
0x14000e1db  mov     [rax+14h], sil
0x14000e1df  mov     dword ptr [rax+10h], 746E6957h
0x14000e1e6  mov     [rax+30h], r12b
0x14000e1ea  call    cs:__imp_KeInitializeSpinLock
0x14000e1f1  nop     dword ptr [rax+rax+00h]
0x14000e1f6  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x14000e1fd  mov     eax, 1
0x14000e202  mov     [rbx+40h], eax
0x14000e205  mov     [rbx+8Ch], eax
0x14000e20b  mov     dword ptr [rbx+90h], 4
0x14000e215  mov     [rbx+6Ch], r12d
0x14000e219  mov     [rbx+60h], r12
0x14000e21d  movups  xmm0, cs:ServerInterfaceGuid
0x14000e224  movdqu  xmmword ptr [rbx+44h], xmm0
0x14000e229  test    sil, sil
0x14000e22c  jz      short loc_14000E237
0x14000e22e  mov     [rdi+0A8h], rbx
0x14000e235  jmp     short loc_14000E23E
0x14000e237  mov     [rdi+0B0h], rbx
0x14000e23e  add     [rdi+0B8h], eax
0x14000e244  test    r14d, r14d
0x14000e247  jnz     short loc_14000E24C
0x14000e249  mov     [r15], rdi
0x14000e24c  mov     eax, r14d
0x14000e24f  mov     rcx, [rbp+47h+var_50]
0x14000e253  xor     rcx, rsp; StackCookie
0x14000e256  call    __security_check_cookie
0x14000e25b  add     rsp, 0D8h
0x14000e262  pop     r15
0x14000e264  pop     r14
0x14000e266  pop     r13
0x14000e268  pop     r12
0x14000e26a  pop     rdi
0x14000e26b  pop     rsi
0x14000e26c  pop     rbx
0x14000e26d  pop     rbp
0x14000e26e  retn
```
