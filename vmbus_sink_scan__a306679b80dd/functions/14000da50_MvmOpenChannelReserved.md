# MvmOpenChannelReserved

- ea: `0x14000da50`
- end: `0x14000dbab`
- name: `MvmOpenChannelReserved`
- size: `347`
- prototype: `char __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x14000da50`
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
char __fastcall MvmOpenChannelReserved(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v6; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdi
  char v11; // al
  __int64 v12; // rsi
  int VpRegister; // eax
  __int64 v14; // rcx
  _QWORD v15[38]; // [rsp+20h] [rbp-E0h] BYREF

  memset(v15, 0, 0xF4u);
  v6 = *(_QWORD *)(a1 + 40);
  if ( *(_DWORD *)(v6 + 160) < 0x40000u )
  {
    *(_DWORD *)(v6 + 208) = 14;
    return 0;
  }
  v8 = MvmpEstablishGhcbPage(v6);
  LOBYTE(v9) = 1;
  v10 = v8;
  v11 = MvmpEstablishMessagePage(*(_QWORD *)(a1 + 40), v8, v9);
  v12 = *(_QWORD *)(a1 + 40);
  if ( !v11 )
  {
    MvmpReleaseGhcbPage(*(_QWORD *)(a1 + 40), v10);
    return 0;
  }
  memset(v15, 0, 0xF4u);
  HIDWORD(v15[1]) = *(_DWORD *)(a1 + 48);
  v15[3] = __PAIR64__(a3, a2);
  VpRegister = MvmpGetVpRegister(v12, v10, 1073741826, 2, 0x120000001CLL);
  v14 = *(_QWORD *)(a1 + 40);
  LODWORD(v15[2]) = VpRegister;
  HIDWORD(v15[2]) = *(_DWORD *)(v14 + 92);
  MvmpSendMessageSynchronous(v14, v10, (unsigned int *)v15);
  MvmpReceiveMessageIgnoreUnsupported(*(_QWORD *)(a1 + 40), v10, v15);
  MvmpReleaseMessagePage(*(_QWORD *)(a1 + 40), v10);
  MvmpReleaseGhcbPage(*(_QWORD *)(a1 + 40), v10);
  if ( v15[0] != 0x600000014LL || HIDWORD(v15[1]) != *(_DWORD *)(a1 + 48) )
    __fastfail(0x3Au);
  if ( HIDWORD(v15[2]) )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 208LL) = 13;
    return 0;
  }
  *(_BYTE *)(a1 + 56) = 1;
  return 1;
}

```

## disassembly

```asm
0x14000da50  push    rbp
0x14000da52  push    rbx
0x14000da53  push    rsi
0x14000da54  push    rdi
0x14000da55  push    r14
0x14000da57  push    r15
0x14000da59  lea     rbp, [rsp-28h]
0x14000da5e  sub     rsp, 128h
0x14000da65  mov     r14d, r8d
0x14000da68  mov     r15d, edx
0x14000da6b  mov     rbx, rcx
0x14000da6e  xor     edx, edx; Val
0x14000da70  mov     r8d, 0F4h; Size
0x14000da76  lea     rcx, [rsp+150h+var_130]; void *
0x14000da7b  call    memset
0x14000da80  mov     rcx, [rbx+28h]
0x14000da84  cmp     dword ptr [rcx+0A0h], 40000h
0x14000da8e  jnb     short loc_14000DAAD
0x14000da90  mov     dword ptr [rcx+0D0h], 0Eh
0x14000da9a  xor     al, al
0x14000da9c  add     rsp, 128h
0x14000daa3  pop     r15
0x14000daa5  pop     r14
0x14000daa7  pop     rdi
0x14000daa8  pop     rsi
0x14000daa9  pop     rbx
0x14000daaa  pop     rbp
0x14000daab  retn
0x14000daad  call    MvmpEstablishGhcbPage
0x14000dab2  mov     rcx, [rbx+28h]
0x14000dab6  mov     r8b, 1
0x14000dab9  mov     rdx, rax
0x14000dabc  mov     rdi, rax
0x14000dabf  call    MvmpEstablishMessagePage
0x14000dac4  mov     rsi, [rbx+28h]
0x14000dac8  test    al, al
0x14000daca  jnz     short loc_14000DAD9
0x14000dacc  mov     rdx, rdi
0x14000dacf  mov     rcx, rsi
0x14000dad2  call    MvmpReleaseGhcbPage
0x14000dad7  jmp     short loc_14000DA9A
0x14000dad9  xor     edx, edx; Val
0x14000dadb  lea     rcx, [rsp+150h+var_130]; void *
0x14000dae0  mov     r8d, 0F4h; Size
0x14000dae6  call    memset
0x14000daeb  mov     eax, [rbx+30h]
0x14000daee  mov     r9d, 2
0x14000daf4  mov     r8d, 40000002h
0x14000dafa  mov     [rsp+150h+var_124], eax
0x14000dafe  mov     rdx, rdi
0x14000db01  mov     dword ptr [rsp+150h+var_130+4], 12h
0x14000db09  mov     rcx, rsi
0x14000db0c  mov     dword ptr [rsp+150h+var_130], 1Ch
0x14000db14  mov     [rsp+150h+var_114], r14d
0x14000db19  mov     [rsp+150h+var_118], r15d
0x14000db1e  call    MvmpGetVpRegister
0x14000db23  mov     rcx, [rbx+28h]
0x14000db27  lea     r8, [rsp+150h+var_130]
0x14000db2c  mov     [rsp+150h+var_120], eax
0x14000db30  mov     rdx, rdi
0x14000db33  mov     eax, [rcx+5Ch]
0x14000db36  mov     [rsp+150h+var_11C], eax
0x14000db3a  call    MvmpSendMessageSynchronous
0x14000db3f  mov     rcx, [rbx+28h]
0x14000db43  lea     r8, [rsp+150h+var_130]
0x14000db48  mov     rdx, rdi
0x14000db4b  call    MvmpReceiveMessageIgnoreUnsupported
0x14000db50  mov     rcx, [rbx+28h]
0x14000db54  mov     rdx, rdi
0x14000db57  call    MvmpReleaseMessagePage
0x14000db5c  mov     rcx, [rbx+28h]
0x14000db60  mov     rdx, rdi
0x14000db63  call    MvmpReleaseGhcbPage
0x14000db68  cmp     dword ptr [rsp+150h+var_130+4], 6
0x14000db6d  jnz     short loc_14000DBA4
0x14000db6f  cmp     dword ptr [rsp+150h+var_130], 14h
0x14000db74  jnz     short loc_14000DBA4
0x14000db76  mov     eax, [rbx+30h]
0x14000db79  cmp     [rsp+150h+var_124], eax
0x14000db7d  jnz     short loc_14000DBA4
0x14000db7f  cmp     [rsp+150h+var_11C], 0
0x14000db84  jz      short loc_14000DB99
0x14000db86  mov     rax, [rbx+28h]
0x14000db8a  mov     dword ptr [rax+0D0h], 0Dh
0x14000db94  jmp     loc_14000DA9A
0x14000db99  mov     byte ptr [rbx+38h], 1
0x14000db9d  mov     al, 1
0x14000db9f  jmp     loc_14000DA9C
0x14000dba4  mov     ecx, 3Ah ; ':'
0x14000dba9  int     29h; Win8: RtlFailFast(ecx)
```
