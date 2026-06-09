# MvmOpenChannel

- ea: `0x14000d910`
- end: `0x14000da48`
- name: `MvmOpenChannel`
- size: `312`
- prototype: `char __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000a9e0`

## callees

- `0x14000d910`
- `0x14000dd98`
- `0x14000e0a0`
- `0x14000e0f0`
- `0x14000e314`
- `0x14000e8ec`
- `0x14000e910`
- `0x14000e9f4`
- `0x140017540`

## pseudocode

```c
char __fastcall MvmOpenChannel(__int64 a1, int a2, int a3)
{
  __int64 v6; // rdi
  __int64 v8; // rcx
  int VpRegister; // eax
  __int64 v10; // rcx
  _QWORD v11[36]; // [rsp+20h] [rbp-E0h] BYREF

  memset(v11, 0, 0xF4u);
  v6 = MvmpEstablishGhcbPage(*(_QWORD *)(a1 + 40));
  if ( !(unsigned __int8)MvmpEstablishMessagePage(*(_QWORD *)(a1 + 40), v6, 0) )
  {
    MvmpReleaseGhcbPage(*(_QWORD *)(a1 + 40), v6);
    return 0;
  }
  memset(v11, 0, 0xF4u);
  v8 = *(_QWORD *)(a1 + 40);
  HIDWORD(v11[1]) = *(_DWORD *)(a1 + 48);
  HIDWORD(v11[3]) = a3;
  HIDWORD(v11[2]) = a2;
  VpRegister = MvmpGetVpRegister(v8, v6, 1073741826, 2, 0x50000009CLL);
  v10 = *(_QWORD *)(a1 + 40);
  LODWORD(v11[3]) = VpRegister;
  MvmpSendMessageSynchronous(v10, v6, (unsigned int *)v11);
  MvmpReceiveMessageIgnoreUnsupported(*(_QWORD *)(a1 + 40), v6, v11);
  MvmpReleaseMessagePage(*(_QWORD *)(a1 + 40), v6);
  MvmpReleaseGhcbPage(*(_QWORD *)(a1 + 40), v6);
  if ( v11[0] != 0x600000014LL || *(_QWORD *)((char *)&v11[1] + 4) != *(_DWORD *)(a1 + 48) )
    __fastfail(0x3Au);
  if ( HIDWORD(v11[2]) )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 208LL) = 13;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x14000d910  push    rbp
0x14000d912  push    rbx
0x14000d913  push    rsi
0x14000d914  push    rdi
0x14000d915  push    r14
0x14000d917  lea     rbp, [rsp-20h]
0x14000d91c  sub     rsp, 120h
0x14000d923  mov     esi, r8d
0x14000d926  mov     r14d, edx
0x14000d929  mov     rbx, rcx
0x14000d92c  xor     edx, edx; Val
0x14000d92e  mov     r8d, 0F4h; Size
0x14000d934  lea     rcx, [rsp+140h+var_120]; void *
0x14000d939  call    memset
0x14000d93e  mov     rcx, [rbx+28h]
0x14000d942  call    MvmpEstablishGhcbPage
0x14000d947  mov     rcx, [rbx+28h]
0x14000d94b  xor     r8d, r8d
0x14000d94e  mov     rdx, rax
0x14000d951  mov     rdi, rax
0x14000d954  call    MvmpEstablishMessagePage
0x14000d959  test    al, al
0x14000d95b  jnz     short loc_14000D97A
0x14000d95d  mov     rcx, [rbx+28h]
0x14000d961  mov     rdx, rdi
0x14000d964  call    MvmpReleaseGhcbPage
0x14000d969  xor     al, al
0x14000d96b  add     rsp, 120h
0x14000d972  pop     r14
0x14000d974  pop     rdi
0x14000d975  pop     rsi
0x14000d976  pop     rbx
0x14000d977  pop     rbp
0x14000d978  retn
0x14000d97a  xor     edx, edx; Val
0x14000d97c  lea     rcx, [rsp+140h+var_120]; void *
0x14000d981  mov     r8d, 0F4h; Size
0x14000d987  call    memset
0x14000d98c  mov     eax, [rbx+30h]
0x14000d98f  mov     r9d, 2
0x14000d995  mov     rcx, [rbx+28h]
0x14000d999  mov     r8d, 40000002h
0x14000d99f  mov     rdx, rdi
0x14000d9a2  mov     dword ptr [rsp+140h+var_114], eax
0x14000d9a6  mov     dword ptr [rsp+140h+var_120+4], 5
0x14000d9ae  mov     dword ptr [rsp+140h+var_120], 9Ch
0x14000d9b6  mov     [rsp+140h+var_104], esi
0x14000d9ba  mov     [rsp+140h+var_10C], r14d
0x14000d9bf  call    MvmpGetVpRegister
0x14000d9c4  mov     rcx, [rbx+28h]
0x14000d9c8  lea     r8, [rsp+140h+var_120]
0x14000d9cd  mov     rdx, rdi
0x14000d9d0  mov     [rsp+140h+var_108], eax
0x14000d9d4  call    MvmpSendMessageSynchronous
0x14000d9d9  mov     rcx, [rbx+28h]
0x14000d9dd  lea     r8, [rsp+140h+var_120]
0x14000d9e2  mov     rdx, rdi
0x14000d9e5  call    MvmpReceiveMessageIgnoreUnsupported
0x14000d9ea  mov     rcx, [rbx+28h]
0x14000d9ee  mov     rdx, rdi
0x14000d9f1  call    MvmpReleaseMessagePage
0x14000d9f6  mov     rcx, [rbx+28h]
0x14000d9fa  mov     rdx, rdi
0x14000d9fd  call    MvmpReleaseGhcbPage
0x14000da02  cmp     dword ptr [rsp+140h+var_120+4], 6
0x14000da07  jnz     short loc_14000DA41
0x14000da09  cmp     dword ptr [rsp+140h+var_120], 14h
0x14000da0e  jnz     short loc_14000DA41
0x14000da10  mov     eax, [rbx+30h]
0x14000da13  cmp     dword ptr [rsp+140h+var_114], eax
0x14000da17  jnz     short loc_14000DA41
0x14000da19  cmp     dword ptr [rsp+140h+var_114+4], 0
0x14000da1e  jnz     short loc_14000DA41
0x14000da20  cmp     [rsp+140h+var_10C], 0
0x14000da25  jz      short loc_14000DA3A
0x14000da27  mov     rax, [rbx+28h]
0x14000da2b  mov     dword ptr [rax+0D0h], 0Dh
0x14000da35  jmp     loc_14000D969
0x14000da3a  mov     al, 1
0x14000da3c  jmp     loc_14000D96B
0x14000da41  mov     ecx, 3Ah ; ':'
0x14000da46  int     29h; Win8: RtlFailFast(ecx)
```
