# WapHttp3StreamSendProcessIo

- ea: `0x18007ff20`
- end: `0x180080237`
- name: `WapHttp3StreamSendProcessIo`
- size: `791`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a130`
- `0x18007fcb0`

## callees

- `0x18005fd88`
- `0x1800722f0`
- `0x18007b37c`
- `0x18007f260`
- `0x18007f2bc`
- `0x18007ff20`
- `0x18008033c`
- `0x180080394`
- `0x180080830`
- `0x1800937d8`
- `0x180093dc0`
- `0x180094c0c`
- `0x1800971ec`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800800fa`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800800fa`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18008009e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18008009e`

## pseudocode

```c
__int64 __fastcall WapHttp3StreamSendProcessIo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 a4,
        unsigned __int8 a5)
{
  char v5; // bp
  unsigned int Error; // edi
  __int64 v8; // rsi
  char *v9; // r13
  _DWORD *v10; // r14
  _QWORD *v11; // r12
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  unsigned int v20; // eax
  int v22; // [rsp+28h] [rbp-A0h]
  int v23; // [rsp+30h] [rbp-98h]
  int v24; // [rsp+38h] [rbp-90h]
  int v25; // [rsp+40h] [rbp-88h]
  unsigned int v26; // [rsp+78h] [rbp-50h] BYREF

  v5 = a4;
  Error = a2;
  v26 = a3;
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
  {
    v25 = a5;
    v24 = a4;
    v23 = a3;
    v22 = a2;
    WPP_SF_qqDdll(a1, a2, a3, a1, *(_QWORD *)(a1 + 8));
    a3 = v26;
  }
  v8 = *(_QWORD *)(a1 + 8);
  v9 = (char *)(a1 + 148);
  v10 = (_DWORD *)(a1 + 144);
  v11 = (_QWORD *)(a1 + 136);
  v12 = v8 + 184;
  if ( !v5 )
    goto LABEL_5;
  while ( 1 )
  {
    WapHttp3StreamUpdateTimerOnCompletion(v8, v12);
    a3 = v26;
LABEL_5:
    if ( Error )
      break;
    *(_DWORD *)(a1 + 152) += a3;
    v13 = *(unsigned int *)(a1 + 152);
    v26 = 0;
    if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
      WPP_SF_qddl(v13, a2, a3, *v11, *v10, v13, (unsigned __int8)*v9, v24, v25);
    v14 = *v10;
    v15 = *(_DWORD *)(a1 + 152);
    if ( v5 )
    {
      if ( v14 == v15 )
        break;
    }
    if ( (Microsoft_Windows_WebIOEnableBits & 0x100) != 0 )
      McTemplateU0ppxppqxxxtt_EventWriteTransfer(
        (unsigned __int8)*v9,
        (unsigned int)NetSocketSendEntity,
        *(_QWORD *)(v8 + 8),
        0,
        0,
        *(_BYTE *)v11 + v15,
        a1 + 24,
        0,
        0,
        *(_QWORD *)(v8 + 24),
        v14 - v15,
        *v9,
        0);
    WapHttp3StreamUpdateTimerOnRequest(v8, v8 + 184);
    StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v8 + 40) + 8LL));
    Error = WaHttpApiStreamSendEntityBody(
              **(_QWORD **)(v8 + 40),
              *(_QWORD *)(v8 + 24),
              *(_DWORD *)v11 + *(_DWORD *)(a1 + 152),
              *v10 - *(_DWORD *)(a1 + 152),
              *v9,
              a1 + 32,
              (__int64)&v26);
    if ( Error == 997 )
      goto LABEL_28;
    CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v8 + 40) + 8LL));
    v12 = v8 + 184;
    v5 = 1;
    v10 = (_DWORD *)(a1 + 144);
    v11 = (_QWORD *)(a1 + 136);
  }
  Error = WapHttp3StreamGetError(Error, v8);
  *(_DWORD *)(a1 + 112) = Error;
  v19 = *(unsigned int *)(a1 + 152);
  *(_QWORD *)(a1 + 120) = v19;
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_Dd(v17, v16, v18, Error, v19, v22, v23);
  *(_QWORD *)(v8 + 280) = 0;
  if ( !Error )
  {
    if ( *v9 && *(_BYTE *)(v8 + 268) )
    {
      v20 = WapHttp3StreamNotifyDisconnect(v8, *(_QWORD *)(a1 + 120), *(_QWORD *)(a1 + 96), *(_QWORD *)(a1 + 104));
      Error = v20;
      if ( v20 == 997 )
      {
        *(_BYTE *)(a1 + 132) = 1;
        goto LABEL_26;
      }
      *(_DWORD *)(a1 + 112) = v20;
    }
LABEL_23:
    if ( !*(_BYTE *)(a1 + 132) )
    {
      *(_BYTE *)(a1 + 132) = 1;
      if ( !a5 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 96))(
          *(_QWORD *)(a1 + 104),
          *(unsigned int *)(a1 + 112),
          *(_QWORD *)(a1 + 120));
        Error = 997;
      }
    }
    goto LABEL_26;
  }
  if ( Error != 997 )
    goto LABEL_23;
LABEL_26:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF) == 1 )
    WapHttpApiFreeIoContext(a1);
LABEL_28:
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 185, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, Error);
  return Error;
}

```

## disassembly

```asm
0x18007ff20  mov     [rsp+arg_18], rbx
0x18007ff25  push    rbp
0x18007ff26  push    rsi
0x18007ff27  push    rdi
0x18007ff28  push    r12
0x18007ff2a  push    r13
0x18007ff2c  push    r14
0x18007ff2e  push    r15
0x18007ff30  sub     rsp, 90h
0x18007ff37  mov     rax, cs:__security_cookie
0x18007ff3e  xor     rax, rsp
0x18007ff41  mov     [rsp+0C8h+var_48], rax
0x18007ff49  movzx   ebp, r9b
0x18007ff4d  mov     edi, edx
0x18007ff4f  mov     rbx, rcx
0x18007ff52  mov     [rsp+0C8h+var_50], r8d
0x18007ff57  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007ff5e  jz      short loc_18007FF8F
0x18007ff60  movzx   eax, [rsp+0C8h+arg_20]
0x18007ff68  mov     r9, rcx
0x18007ff6b  mov     dword ptr [rsp+0C8h+var_88], eax
0x18007ff6f  mov     rax, [rcx+8]
0x18007ff73  mov     [rsp+0C8h+var_90], ebp
0x18007ff77  mov     dword ptr [rsp+0C8h+var_98], r8d
0x18007ff7c  mov     dword ptr [rsp+0C8h+var_A0], edx
0x18007ff80  mov     [rsp+0C8h+var_A8], rax
0x18007ff85  call    WPP_SF_qqDdll
0x18007ff8a  mov     r8d, [rsp+0C8h+var_50]
0x18007ff8f  mov     rsi, [rbx+8]
0x18007ff93  lea     r13, [rbx+94h]
0x18007ff9a  lea     r14, [rbx+90h]
0x18007ffa1  lea     r12, [rbx+88h]
0x18007ffa8  lea     rax, [rsi+0B8h]
0x18007ffaf  test    bpl, bpl
0x18007ffb2  jz      short loc_18007FFC4
0x18007ffb4  mov     rdx, rax
0x18007ffb7  mov     rcx, rsi
0x18007ffba  call    WapHttp3StreamUpdateTimerOnCompletion
0x18007ffbf  mov     r8d, [rsp+0C8h+var_50]
0x18007ffc4  mov     r15, r13
0x18007ffc7  test    edi, edi
0x18007ffc9  jnz     loc_180080123
0x18007ffcf  add     [rbx+98h], r8d
0x18007ffd6  mov     ecx, [rbx+98h]
0x18007ffdc  mov     [rsp+0C8h+var_50], edi
0x18007ffe0  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007ffe7  jz      short loc_180080006
0x18007ffe9  movzx   eax, byte ptr [r13+0]
0x18007ffee  mov     r9, [r12]
0x18007fff2  mov     dword ptr [rsp+0C8h+var_98], eax
0x18007fff6  mov     eax, [r14]
0x18007fff9  mov     dword ptr [rsp+0C8h+var_A0], ecx
0x18007fffd  mov     dword ptr [rsp+0C8h+var_A8], eax
0x180080001  call    WPP_SF_qddl
0x180080006  mov     eax, [r14]
0x180080009  mov     r8d, [rbx+98h]
0x180080010  test    bpl, bpl
0x180080013  jz      short loc_18008001E
0x180080015  cmp     eax, r8d
0x180080018  jz      loc_180080123
0x18008001e  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 1
0x180080025  jz      short loc_180080087
0x180080027  movzx   ecx, byte ptr [r15]
0x18008002b  lea     rdx, [rbx+18h]
0x18008002f  mov     [rsp+0C8h+var_68], 0
0x180080037  sub     eax, r8d
0x18008003a  add     r8, [r12]
0x18008003e  xor     r9d, r9d
0x180080041  mov     [rsp+0C8h+var_70], ecx
0x180080045  mov     [rsp+0C8h+var_78], rax
0x18008004a  mov     rax, [rsi+18h]
0x18008004e  mov     [rsp+0C8h+var_80], rax
0x180080053  mov     [rsp+0C8h+var_88], 0
0x18008005c  mov     [rsp+0C8h+var_90], 0
0x180080064  mov     [rsp+0C8h+var_98], rdx
0x180080069  lea     rdx, NetSocketSendEntity
0x180080070  mov     [rsp+0C8h+var_A0], r8
0x180080075  mov     r8, [rsi+8]
0x180080079  mov     [rsp+0C8h+var_A8], 0
0x180080082  call    McTemplateU0ppxppqxxxtt_EventWriteTransfer
0x180080087  lea     rdx, [rsi+0B8h]
0x18008008e  mov     rcx, rsi
0x180080091  call    WapHttp3StreamUpdateTimerOnRequest
0x180080096  mov     rcx, [rsi+28h]
0x18008009a  mov     rcx, [rcx+8]; pio
0x18008009e  call    cs:__imp_StartThreadpoolIo
0x1800800a5  nop     dword ptr [rax+rax+00h]
0x1800800aa  mov     r8d, [rbx+98h]
0x1800800b1  lea     rax, [rbx+20h]
0x1800800b5  mov     rcx, [rsi+28h]
0x1800800b9  lea     rdx, [rsp+0C8h+var_50]
0x1800800be  mov     r9d, [r14]
0x1800800c1  mov     [rsp+0C8h+var_98], rdx
0x1800800c6  sub     r9d, r8d
0x1800800c9  add     r8, [r12]
0x1800800cd  mov     rcx, [rcx]
0x1800800d0  mov     rdx, [rsi+18h]
0x1800800d4  mov     [rsp+0C8h+var_A0], rax
0x1800800d9  mov     al, [r15]
0x1800800dc  mov     byte ptr [rsp+0C8h+var_A8], al
0x1800800e0  call    WaHttpApiStreamSendEntityBody
0x1800800e5  mov     edi, eax
0x1800800e7  cmp     eax, 3E5h
0x1800800ec  jz      loc_1800801E7
0x1800800f2  mov     rcx, [rsi+28h]
0x1800800f6  mov     rcx, [rcx+8]; pio
0x1800800fa  call    cs:__imp_CancelThreadpoolIo
0x180080101  nop     dword ptr [rax+rax+00h]
0x180080106  lea     rax, [rsi+0B8h]
0x18008010d  mov     bpl, 1
0x180080110  lea     r14, [rbx+90h]
0x180080117  lea     r12, [rbx+88h]
0x18008011e  jmp     loc_18007FFB4
0x180080123  mov     rdx, rsi
0x180080126  mov     ecx, edi
0x180080128  call    WapHttp3StreamGetError
0x18008012d  mov     edi, eax
0x18008012f  mov     [rbx+70h], eax
0x180080132  mov     eax, [rbx+98h]
0x180080138  mov     [rbx+78h], rax
0x18008013c  test    byte ptr cs:xmmword_1800AD720+3, 4
0x180080143  jz      short loc_180080151
0x180080145  mov     r9d, edi
0x180080148  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18008014c  call    WPP_SF_Dd
0x180080151  xor     ebp, ebp
0x180080153  mov     [rsi+118h], rbp
0x18008015a  test    edi, edi
0x18008015c  jnz     short loc_180080197
0x18008015e  cmp     [r15], bpl
0x180080161  jz      short loc_18008019F
0x180080163  cmp     [rsi+10Ch], bpl
0x18008016a  jz      short loc_18008019F
0x18008016c  mov     r9, [rbx+68h]
0x180080170  mov     rcx, rsi
0x180080173  mov     r8, [rbx+60h]
0x180080177  mov     rdx, [rbx+78h]
0x18008017b  call    WapHttp3StreamNotifyDisconnect
0x180080180  mov     edi, eax
0x180080182  cmp     eax, 3E5h
0x180080187  jnz     short loc_180080192
0x180080189  mov     byte ptr [rbx+84h], 1
0x180080190  jmp     short loc_1800801D2
0x180080192  mov     [rbx+70h], eax
0x180080195  jmp     short loc_18008019F
0x180080197  cmp     edi, 3E5h
0x18008019d  jz      short loc_1800801D2
0x18008019f  cmp     [rbx+84h], bpl
0x1800801a6  jnz     short loc_1800801D2
0x1800801a8  mov     byte ptr [rbx+84h], 1
0x1800801af  cmp     [rsp+0C8h+arg_20], bpl
0x1800801b7  jnz     short loc_1800801D2
0x1800801b9  mov     r8, [rbx+78h]
0x1800801bd  mov     edx, [rbx+70h]
0x1800801c0  mov     rcx, [rbx+68h]
0x1800801c4  mov     rax, [rbx+60h]
0x1800801c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800801cd  mov     edi, 3E5h
0x1800801d2  or      eax, 0FFFFFFFFh
0x1800801d5  lock xadd [rbx+4], eax
0x1800801da  cmp     eax, 1
0x1800801dd  jnz     short loc_1800801E7
0x1800801df  mov     rcx, rbx
0x1800801e2  call    WapHttpApiFreeIoContext
0x1800801e7  test    byte ptr cs:xmmword_1800AD720+3, 4
0x1800801ee  jz      short loc_180080209
0x1800801f0  mov     edx, 0B9h
0x1800801f5  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x1800801fc  mov     ecx, 41Ah
0x180080201  mov     r9d, edi
0x180080204  call    WPP_SF_d
0x180080209  mov     eax, edi
0x18008020b  mov     rcx, [rsp+0C8h+var_48]
0x180080213  xor     rcx, rsp; StackCookie
0x180080216  call    __security_check_cookie
0x18008021b  mov     rbx, [rsp+0C8h+arg_18]
0x180080223  add     rsp, 90h
0x18008022a  pop     r15
0x18008022c  pop     r14
0x18008022e  pop     r13
0x180080230  pop     r12
0x180080232  pop     rdi
0x180080233  pop     rsi
0x180080234  pop     rbp
0x180080235  retn
```
