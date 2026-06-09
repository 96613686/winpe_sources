# TpmTransportSpbI2CNTCDevice::SubmitCommand(uchar *,uint,int)

- ea: `0x1400275d0`
- end: `0x140027769`
- name: `?SubmitCommand@TpmTransportSpbI2CNTCDevice@@UEAAJPEAEIH@Z`
- size: `409`
- prototype: `__int64 __fastcall(TpmTransportSpbI2CNTCDevice *__hidden this, unsigned __int8 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400078b8`
- `0x140025d5c`
- `0x140026924`
- `0x140026a68`
- `0x1400275d0`
- `0x140039740`
- `0x140039840`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x14002761a`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14002761a`

## pseudocode

```c
int __fastcall TpmTransportSpbI2CNTCDevice::SubmitCommand(
        TpmTransportSpbI2CNTCDevice *this,
        unsigned __int8 *a2,
        unsigned int a3,
        int a4)
{
  __int64 v8; // rbx
  __int64 v9; // rbx
  int result; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // esi
  unsigned __int8 v14[4]; // [rsp+30h] [rbp-40h] BYREF
  __int16 v15; // [rsp+34h] [rbp-3Ch] BYREF
  __int16 v16; // [rsp+38h] [rbp-38h] BYREF
  char v17; // [rsp+40h] [rbp-30h] BYREF
  _OWORD v18[2]; // [rsp+41h] [rbp-2Fh] BYREF

  v14[0] = 0;
  v15 = 0x4000;
  v16 = 0x2000;
  v8 = MEMORY[0xFFFFF78000000320];
  v9 = 0x989680uLL / KeQueryTimeIncrement() + v8;
  while ( 1 )
  {
    result = TpmTransportSpbDevice::SPBWrite(this, &v15, 2u);
    if ( result < 0 )
      return result;
    result = TpmTransportSpbDevice::SPBSequence(this, 0, v14, 1u, 0);
    if ( result < 0 )
      return result;
    if ( (v14[0] & 0x40) != 0 )
      goto LABEL_12;
    result = TpmTransportSpbDevice::Idle(this, 100, a4 != 0);
    if ( result < 0 )
      return result;
    if ( MEMORY[0xFFFFF78000000320] >= v9 )
    {
      if ( (v14[0] & 0x40) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids);
        return -1073741434;
      }
LABEL_12:
      v11 = 0;
      while ( 1 )
      {
        v17 = 32;
        v12 = a3 - v11;
        v18[0] = 0;
        if ( a3 - v11 > 0x20 )
          v12 = 32;
        v18[1] = 0;
        v13 = v12 + 1;
        memmove(v18, &a2[v11], v12);
        result = TpmTransportSpbDevice::SPBWrite(this, &v17, v13);
        if ( result < 0 )
          break;
        v11 = v13 + v11 - 1;
        if ( v11 >= a3 )
          return TpmTransportSpbDevice::SPBWrite(this, &v16, 2u);
      }
      return result;
    }
  }
}

```

## disassembly

```asm
0x1400275d0  mov     [rsp-28h+arg_18], rbx
0x1400275d5  push    rbp
0x1400275d6  push    rsi
0x1400275d7  push    rdi
0x1400275d8  push    r14
0x1400275da  push    r15
0x1400275dc  mov     rbp, rsp
0x1400275df  sub     rsp, 70h
0x1400275e3  mov     rax, cs:__security_cookie
0x1400275ea  xor     rax, rsp
0x1400275ed  mov     [rbp+var_8], rax
0x1400275f1  mov     [rbp+var_40], 0
0x1400275f5  mov     rbx, 0FFFFF78000000320h
0x1400275ff  mov     [rbp+var_3C], 4000h
0x140027605  mov     esi, r9d
0x140027608  mov     [rbp+var_38], 2000h
0x14002760e  mov     r14d, r8d
0x140027611  mov     r15, rdx
0x140027614  mov     rdi, rcx
0x140027617  mov     rbx, [rbx]
0x14002761a  call    cs:__imp_KeQueryTimeIncrement
0x140027621  nop     dword ptr [rax+rax+00h]
0x140027626  mov     ecx, eax
0x140027628  xor     edx, edx
0x14002762a  mov     eax, 989680h
0x14002762f  div     rcx
0x140027632  add     rbx, rax
0x140027635  mov     r8d, 2; unsigned int
0x14002763b  lea     rdx, [rbp+var_3C]; void *
0x14002763f  mov     rcx, rdi; this
0x140027642  call    ?SPBWrite@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBWrite(void *,uint)
0x140027647  test    eax, eax
0x140027649  js      loc_140027748
0x14002764f  mov     r9d, 1; unsigned int
0x140027655  mov     [rsp+70h+var_50], 0; unsigned int *
0x14002765e  lea     r8, [rbp+var_40]; unsigned __int8 *
0x140027662  xor     edx, edx; unsigned __int8
0x140027664  mov     rcx, rdi; this
0x140027667  call    ?SPBSequence@TpmTransportSpbDevice@@IEAAJEPEAEIPEAI@Z; TpmTransportSpbDevice::SPBSequence(uchar,uchar *,uint,uint *)
0x14002766c  test    eax, eax
0x14002766e  js      loc_140027748
0x140027674  mov     al, [rbp+var_40]
0x140027677  test    al, 40h
0x140027679  jnz     short loc_1400276E2
0x14002767b  test    esi, esi
0x14002767d  mov     edx, 64h ; 'd'; __int64
0x140027682  mov     rcx, rdi; this
0x140027685  setnz   r8b; bool
0x140027689  call    ?Idle@TpmTransportSpbDevice@@IEAAJ_J_N@Z; TpmTransportSpbDevice::Idle(__int64,bool)
0x14002768e  test    eax, eax
0x140027690  js      loc_140027748
0x140027696  mov     rax, ds:0FFFFF78000000320h
0x1400276a0  cmp     rax, rbx
0x1400276a3  jl      short loc_140027635
0x1400276a5  mov     al, [rbp+var_40]
0x1400276a8  test    al, 40h
0x1400276aa  jnz     short loc_1400276E2
0x1400276ac  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400276b3  lea     rax, WPP_GLOBAL_Control
0x1400276ba  cmp     rcx, rax
0x1400276bd  jz      short loc_1400276DB
0x1400276bf  mov     eax, [rcx+2Ch]
0x1400276c2  test    al, 1
0x1400276c4  jz      short loc_1400276DB
0x1400276c6  mov     rcx, [rcx+18h]
0x1400276ca  lea     r8, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids
0x1400276d1  mov     edx, 1Bh
0x1400276d6  call    WPP_SF_
0x1400276db  mov     eax, 0C0000186h
0x1400276e0  jmp     short loc_140027748
0x1400276e2  xor     ebx, ebx
0x1400276e4  mov     ecx, 20h ; ' '
0x1400276e9  mov     edx, ebx
0x1400276eb  mov     eax, r14d
0x1400276ee  mov     [rbp+var_30], cl
0x1400276f1  sub     eax, ebx
0x1400276f3  xorps   xmm0, xmm0
0x1400276f6  cmp     eax, ecx
0x1400276f8  xorps   xmm1, xmm1
0x1400276fb  movdqu  [rbp+var_2F], xmm0
0x140027700  cmova   eax, ecx
0x140027703  add     rdx, r15; Src
0x140027706  mov     r8d, eax; Size
0x140027709  lea     rcx, [rbp+var_2F]; void *
0x14002770d  movdqu  [rbp+var_1F], xmm1
0x140027712  lea     esi, [rax+1]
0x140027715  call    memmove
0x14002771a  mov     r8d, esi; unsigned int
0x14002771d  lea     rdx, [rbp+var_30]; void *
0x140027721  mov     rcx, rdi; this
0x140027724  call    ?SPBWrite@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBWrite(void *,uint)
0x140027729  test    eax, eax
0x14002772b  js      short loc_140027748
0x14002772d  dec     ebx
0x14002772f  add     ebx, esi
0x140027731  cmp     ebx, r14d
0x140027734  jb      short loc_1400276E4
0x140027736  mov     r8d, 2; unsigned int
0x14002773c  lea     rdx, [rbp+var_38]; void *
0x140027740  mov     rcx, rdi; this
0x140027743  call    ?SPBWrite@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBWrite(void *,uint)
0x140027748  mov     rcx, [rbp+var_8]
0x14002774c  xor     rcx, rsp; StackCookie
0x14002774f  call    __security_check_cookie
0x140027754  mov     rbx, [rsp+70h+arg_18]
0x14002775c  add     rsp, 70h
0x140027760  pop     r15
0x140027762  pop     r14
0x140027764  pop     rdi
0x140027765  pop     rsi
0x140027766  pop     rbp
0x140027767  retn
```
