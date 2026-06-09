# TpmTransportSpbSPINTZDevice::SubmitCommand(uchar *,uint,int)

- ea: `0x140027a80`
- end: `0x140027bb0`
- name: `?SubmitCommand@TpmTransportSpbSPINTZDevice@@UEAAJPEAEIH@Z`
- size: `304`
- prototype: `__int64 __fastcall(TpmTransportSpbSPINTZDevice *__hidden this, unsigned __int8 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400078b8`
- `0x140025d5c`
- `0x1400268c8`
- `0x140026a68`
- `0x140026c00`
- `0x140027a80`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x140027aad`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140027aad`

## pseudocode

```c
__int64 __fastcall TpmTransportSpbSPINTZDevice::SubmitCommand(
        TpmTransportSpbSPINTZDevice *this,
        unsigned __int8 *a2,
        int a3,
        int a4)
{
  __int64 v8; // rsi
  unsigned __int64 TimeIncrement; // rbp
  int v10; // ebx
  __int64 v11; // rsi
  _BYTE v13[72]; // [rsp+20h] [rbp-48h] BYREF

  v13[0] = 0;
  v8 = MEMORY[0xFFFFF78000000320];
  TimeIncrement = KeQueryTimeIncrement();
  v10 = TpmTransportSpbSPIDevice::SPILockBus(this, 1);
  if ( v10 >= 0 )
  {
    v11 = 0x989680 / TimeIncrement + v8;
    while ( 1 )
    {
      v10 = TpmTransportSpbDevice::SPBRead(this, v13, 1u);
      if ( v10 < 0 )
        break;
      if ( v13[0] == 0xAA )
        goto LABEL_12;
      v10 = TpmTransportSpbDevice::Idle(this, 10000, a4 != 0);
      if ( v10 < 0 )
        break;
      if ( MEMORY[0xFFFFF78000000320] >= v11 )
      {
        if ( v13[0] != 0xAA )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids);
          }
          v10 = -1073741434;
          break;
        }
LABEL_12:
        v13[0] = -91;
        v10 = TpmTransportSpbDevice::SPBWrite(this, v13, 1);
        if ( v10 >= 0 )
          v10 = TpmTransportSpbDevice::SPBWrite(this, a2, a3);
        break;
      }
    }
    TpmTransportSpbSPIDevice::SPILockBus(this, 0);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140027a80  push    rbx
0x140027a82  push    rbp
0x140027a83  push    rsi
0x140027a84  push    rdi
0x140027a85  push    r12
0x140027a87  push    r14
0x140027a89  push    r15
0x140027a8b  sub     rsp, 30h
0x140027a8f  mov     [rsp+68h+var_48], 0
0x140027a94  mov     rsi, 0FFFFF78000000320h
0x140027a9e  mov     r12d, r9d
0x140027aa1  mov     r14d, r8d
0x140027aa4  mov     r15, rdx
0x140027aa7  mov     rdi, rcx
0x140027aaa  mov     rsi, [rsi]
0x140027aad  call    cs:__imp_KeQueryTimeIncrement
0x140027ab4  nop     dword ptr [rax+rax+00h]
0x140027ab9  mov     dl, 1; bool
0x140027abb  mov     rcx, rdi; this
0x140027abe  mov     ebp, eax
0x140027ac0  call    ?SPILockBus@TpmTransportSpbSPIDevice@@IEAAJ_N@Z; TpmTransportSpbSPIDevice::SPILockBus(bool)
0x140027ac5  mov     ebx, eax
0x140027ac7  test    eax, eax
0x140027ac9  js      loc_140027B9E
0x140027acf  xor     edx, edx
0x140027ad1  mov     eax, 989680h
0x140027ad6  div     rbp
0x140027ad9  add     rsi, rax
0x140027adc  mov     r8d, 1; unsigned int
0x140027ae2  lea     rdx, [rsp+68h+var_48]; void *
0x140027ae7  mov     rcx, rdi; this
0x140027aea  call    ?SPBRead@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBRead(void *,uint)
0x140027aef  mov     ebx, eax
0x140027af1  test    eax, eax
0x140027af3  js      loc_140027B94
0x140027af9  cmp     [rsp+68h+var_48], 0AAh
0x140027afe  jz      short loc_140027B66
0x140027b00  test    r12d, r12d
0x140027b03  mov     edx, 2710h; __int64
0x140027b08  mov     rcx, rdi; this
0x140027b0b  setnz   r8b; bool
0x140027b0f  call    ?Idle@TpmTransportSpbDevice@@IEAAJ_J_N@Z; TpmTransportSpbDevice::Idle(__int64,bool)
0x140027b14  mov     ebx, eax
0x140027b16  test    eax, eax
0x140027b18  js      short loc_140027B94
0x140027b1a  mov     rax, ds:0FFFFF78000000320h
0x140027b24  cmp     rax, rsi
0x140027b27  jl      short loc_140027ADC
0x140027b29  cmp     [rsp+68h+var_48], 0AAh
0x140027b2e  jz      short loc_140027B66
0x140027b30  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140027b37  lea     rax, WPP_GLOBAL_Control
0x140027b3e  cmp     rcx, rax
0x140027b41  jz      short loc_140027B5F
0x140027b43  mov     eax, [rcx+2Ch]
0x140027b46  test    al, 1
0x140027b48  jz      short loc_140027B5F
0x140027b4a  mov     rcx, [rcx+18h]
0x140027b4e  lea     r8, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids
0x140027b55  mov     edx, 11h
0x140027b5a  call    WPP_SF_
0x140027b5f  mov     ebx, 0C0000186h
0x140027b64  jmp     short loc_140027B94
0x140027b66  mov     r8d, 1; unsigned int
0x140027b6c  mov     [rsp+68h+var_48], 0A5h
0x140027b71  lea     rdx, [rsp+68h+var_48]; void *
0x140027b76  mov     rcx, rdi; this
0x140027b79  call    ?SPBWrite@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBWrite(void *,uint)
0x140027b7e  mov     ebx, eax
0x140027b80  test    eax, eax
0x140027b82  js      short loc_140027B94
0x140027b84  mov     r8d, r14d; unsigned int
0x140027b87  mov     rdx, r15; void *
0x140027b8a  mov     rcx, rdi; this
0x140027b8d  call    ?SPBWrite@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBWrite(void *,uint)
0x140027b92  mov     ebx, eax
0x140027b94  xor     edx, edx; bool
0x140027b96  mov     rcx, rdi; this
0x140027b99  call    ?SPILockBus@TpmTransportSpbSPIDevice@@IEAAJ_N@Z; TpmTransportSpbSPIDevice::SPILockBus(bool)
0x140027b9e  mov     eax, ebx
0x140027ba0  add     rsp, 30h
0x140027ba4  pop     r15
0x140027ba6  pop     r14
0x140027ba8  pop     r12
0x140027baa  pop     rdi
0x140027bab  pop     rsi
0x140027bac  pop     rbp
0x140027bad  pop     rbx
0x140027bae  retn
```
