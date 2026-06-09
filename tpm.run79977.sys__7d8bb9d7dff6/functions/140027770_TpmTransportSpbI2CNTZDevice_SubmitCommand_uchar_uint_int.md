# TpmTransportSpbI2CNTZDevice::SubmitCommand(uchar *,uint,int)

- ea: `0x140027770`
- end: `0x14002783b`
- name: `?SubmitCommand@TpmTransportSpbI2CNTZDevice@@UEAAJPEAEIH@Z`
- size: `203`
- prototype: `__int64 __fastcall(TpmTransportSpbI2CNTZDevice *__hidden this, unsigned __int8 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400078b8`
- `0x140025d5c`
- `0x140026a68`
- `0x140027770`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x140027794`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140027794`

## pseudocode

```c
__int64 __fastcall TpmTransportSpbI2CNTZDevice::SubmitCommand(
        TpmTransportSpbI2CNTZDevice *this,
        unsigned __int8 *a2,
        int a3,
        int a4)
{
  __int64 v8; // rbx
  __int64 v9; // rbx
  unsigned int v10; // ecx
  int v11; // eax

  v8 = MEMORY[0xFFFFF78000000320];
  v9 = 0x989680uLL / KeQueryTimeIncrement() + v8;
  do
  {
    v10 = TpmTransportSpbDevice::SPBWrite(this, a2, a3);
    if ( v10 != -1073741810 )
      break;
    v11 = TpmTransportSpbDevice::Idle(this, 10000, a4 != 0);
    v10 = v11;
    if ( v11 < 0 )
    {
      if ( v11 == -1073741810 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids);
        return (unsigned int)-1073741434;
      }
      return v10;
    }
  }
  while ( MEMORY[0xFFFFF78000000320] < v9 );
  return v10;
}

```

## disassembly

```asm
0x140027770  push    rbx
0x140027772  push    rbp
0x140027773  push    rsi
0x140027774  push    rdi
0x140027775  push    r14
0x140027777  sub     rsp, 20h
0x14002777b  mov     rbx, 0FFFFF78000000320h
0x140027785  mov     r14d, r9d
0x140027788  mov     esi, r8d
0x14002778b  mov     rbp, rdx
0x14002778e  mov     rdi, rcx
0x140027791  mov     rbx, [rbx]
0x140027794  call    cs:__imp_KeQueryTimeIncrement
0x14002779b  nop     dword ptr [rax+rax+00h]
0x1400277a0  mov     r10d, eax
0x1400277a3  xor     edx, edx
0x1400277a5  mov     eax, 989680h
0x1400277aa  div     r10
0x1400277ad  add     rbx, rax
0x1400277b0  mov     r8d, esi; unsigned int
0x1400277b3  mov     rdx, rbp; void *
0x1400277b6  mov     rcx, rdi; this
0x1400277b9  call    ?SPBWrite@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBWrite(void *,uint)
0x1400277be  mov     ecx, eax
0x1400277c0  cmp     eax, 0C000000Eh
0x1400277c5  jnz     short loc_14002782D
0x1400277c7  test    r14d, r14d
0x1400277ca  mov     edx, 2710h; __int64
0x1400277cf  mov     rcx, rdi; this
0x1400277d2  setnz   r8b; bool
0x1400277d6  call    ?Idle@TpmTransportSpbDevice@@IEAAJ_J_N@Z; TpmTransportSpbDevice::Idle(__int64,bool)
0x1400277db  mov     ecx, eax
0x1400277dd  test    eax, eax
0x1400277df  js      short loc_1400277F2
0x1400277e1  mov     rax, ds:0FFFFF78000000320h
0x1400277eb  cmp     rax, rbx
0x1400277ee  jl      short loc_1400277B0
0x1400277f0  jmp     short loc_14002782D
0x1400277f2  cmp     eax, 0C000000Eh
0x1400277f7  jnz     short loc_14002782D
0x1400277f9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140027800  lea     rax, WPP_GLOBAL_Control
0x140027807  cmp     rcx, rax
0x14002780a  jz      short loc_140027828
0x14002780c  mov     eax, [rcx+2Ch]
0x14002780f  test    al, 1
0x140027811  jz      short loc_140027828
0x140027813  mov     rcx, [rcx+18h]
0x140027817  lea     r8, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids
0x14002781e  mov     edx, 1Ah
0x140027823  call    WPP_SF_
0x140027828  mov     ecx, 0C0000186h
0x14002782d  mov     eax, ecx
0x14002782f  add     rsp, 20h
0x140027833  pop     r14
0x140027835  pop     rdi
0x140027836  pop     rsi
0x140027837  pop     rbp
0x140027838  pop     rbx
0x140027839  retn
```
