# tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::evaluate(void)

- ea: `0x1800052a0`
- end: `0x180005464`
- name: `?evaluate@?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@EEAAXXZ`
- size: `452`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800052a0`
- `0x180096170`

## string_xrefs

- `0x180005417`: `CommandReason::process_shutdown_ignored`
- `0x180005319`: `CommandReason::not_started`
- `0x180005365`: `CommandReason::failed`
- `0x1800053e0`: `CommandReason::succeeded`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::evaluate(
        __int64 a1)
{
  __int64 result; // rax
  int v3; // eax
  const char *v4; // rcx
  char v5; // al
  const char *v6; // r8
  const char *v7; // r8
  char v8; // al
  const char *v9; // r9
  const char *v10; // rcx
  char v11; // al
  const char *v12; // rcx
  char v13; // al

  result = *(_QWORD *)(a1 + 264);
  if ( *(_QWORD *)(result + 80) )
  {
    if ( *(_BYTE *)(result + 152) )
      return result;
    *(_BYTE *)(result + 152) = 3;
    *(_WORD *)(result + 154) = 0x4000;
    goto LABEL_4;
  }
  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    v12 = "CommandReason::process_shutdown_ignored";
    v13 = 67;
    v6 = "CommandReason::process_shutdown_ignored";
    do
    {
      ++v12;
      if ( v13 == 58 )
        v6 = v12;
      v13 = *v12;
    }
    while ( *v12 );
    result = *(_QWORD *)(a1 + 264);
    if ( *(_BYTE *)(result + 152) )
      return result;
    *(_WORD *)(result + 154) = 4;
    goto LABEL_37;
  }
  v3 = *(_DWORD *)(a1 + 276);
  if ( v3 != 1 )
  {
    if ( v3 == 3 )
    {
      v7 = "CommandReason::failed";
      v8 = 67;
      v9 = "CommandReason::failed";
      do
      {
        ++v7;
        if ( v8 == 58 )
          v9 = v7;
        v8 = *v7;
      }
      while ( *v7 );
      result = *(_QWORD *)(a1 + 264);
      if ( !*(_BYTE *)(result + 152) )
      {
        *(_BYTE *)(result + 152) = 3;
        *(_WORD *)(result + 154) = 3;
        *(_QWORD *)(result + 160) = v9;
      }
      return result;
    }
    result = *(_QWORD *)(a1 + 264);
    if ( (*(_DWORD *)(result + 56) & 0x200) == 0 )
    {
      if ( !*(_BYTE *)(result + 152) )
      {
        *(_BYTE *)(result + 152) = 3;
        *(_WORD *)(result + 154) = 16385;
LABEL_4:
        *(_QWORD *)(result + 160) = 0;
        return result;
      }
      return result;
    }
    v10 = "CommandReason::succeeded";
    v11 = 67;
    v6 = "CommandReason::succeeded";
    do
    {
      ++v10;
      if ( v11 == 58 )
        v6 = v10;
      v11 = *v10;
    }
    while ( *v10 );
    result = *(_QWORD *)(a1 + 264);
    if ( *(_BYTE *)(result + 152) )
      return result;
    *(_WORD *)(result + 154) = 2;
LABEL_37:
    *(_BYTE *)(result + 152) = 1;
    goto LABEL_38;
  }
  v4 = "CommandReason::not_started";
  v5 = 67;
  v6 = "CommandReason::not_started";
  do
  {
    ++v4;
    if ( v5 == 58 )
      v6 = v4;
    v5 = *v4;
  }
  while ( *v4 );
  result = *(_QWORD *)(a1 + 264);
  if ( !*(_BYTE *)(result + 152) )
  {
    *(_BYTE *)(result + 152) = 3;
    *(_WORD *)(result + 154) = 1;
LABEL_38:
    *(_QWORD *)(result + 160) = v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800052a0  push    rbx
0x1800052a2  sub     rsp, 20h
0x1800052a6  mov     rax, [rcx+108h]
0x1800052ad  mov     rbx, rcx
0x1800052b0  cmp     qword ptr [rax+50h], 0
0x1800052b5  jz      short loc_1800052E4
0x1800052b7  cmp     byte ptr [rax+98h], 0
0x1800052be  jnz     loc_18000545E
0x1800052c4  mov     byte ptr [rax+98h], 3
0x1800052cb  mov     word ptr [rax+9Ah], 4000h
0x1800052d4  mov     qword ptr [rax+0A0h], 0
0x1800052df  jmp     loc_18000545E
0x1800052e4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800052eb  jnz     loc_180005417
0x1800052f1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800052f8  test    rax, rax
0x1800052fb  jz      short loc_18000530A
0x1800052fd  call    _guard_dispatch_icall
0x180005302  test    al, al
0x180005304  jnz     loc_180005417
0x18000530a  mov     eax, [rbx+114h]
0x180005310  mov     edx, 1
0x180005315  cmp     eax, edx
0x180005317  jnz     short loc_18000535C
0x180005319  lea     rcx, aCommandreasonN; "CommandReason::not_started"
0x180005320  mov     al, 43h ; 'C'
0x180005322  mov     r8, rcx
0x180005325  add     rcx, rdx
0x180005328  cmp     al, 3Ah ; ':'
0x18000532a  jnz     short loc_18000532F
0x18000532c  mov     r8, rcx
0x18000532f  mov     al, [rcx]
0x180005331  test    al, al
0x180005333  jnz     short loc_180005325
0x180005335  mov     rax, [rbx+108h]
0x18000533c  cmp     byte ptr [rax+98h], 0
0x180005343  jnz     loc_18000545E
0x180005349  mov     byte ptr [rax+98h], 3
0x180005350  mov     [rax+9Ah], dx
0x180005357  jmp     loc_180005457
0x18000535c  mov     ecx, 3
0x180005361  cmp     eax, ecx
0x180005363  jnz     short loc_1800053AF
0x180005365  lea     r8, aCommandreasonF; "CommandReason::failed"
0x18000536c  mov     al, 43h ; 'C'
0x18000536e  mov     r9, r8
0x180005371  add     r8, rdx
0x180005374  cmp     al, 3Ah ; ':'
0x180005376  jnz     short loc_18000537B
0x180005378  mov     r9, r8
0x18000537b  mov     al, [r8]
0x18000537e  test    al, al
0x180005380  jnz     short loc_180005371
0x180005382  mov     rax, [rbx+108h]
0x180005389  cmp     byte ptr [rax+98h], 0
0x180005390  jnz     loc_18000545E
0x180005396  mov     [rax+98h], cl
0x18000539c  mov     [rax+9Ah], cx
0x1800053a3  mov     [rax+0A0h], r9
0x1800053aa  jmp     loc_18000545E
0x1800053af  mov     rax, [rbx+108h]
0x1800053b6  test    dword ptr [rax+38h], 200h
0x1800053bd  jnz     short loc_1800053E0
0x1800053bf  cmp     byte ptr [rax+98h], 0
0x1800053c6  jnz     loc_18000545E
0x1800053cc  mov     [rax+98h], cl
0x1800053d2  mov     word ptr [rax+9Ah], 4001h
0x1800053db  jmp     loc_1800052D4
0x1800053e0  lea     rcx, aCommandreasonS; "CommandReason::succeeded"
0x1800053e7  mov     al, 43h ; 'C'
0x1800053e9  mov     r8, rcx
0x1800053ec  add     rcx, rdx
0x1800053ef  cmp     al, 3Ah ; ':'
0x1800053f1  jnz     short loc_1800053F6
0x1800053f3  mov     r8, rcx
0x1800053f6  mov     al, [rcx]
0x1800053f8  test    al, al
0x1800053fa  jnz     short loc_1800053EC
0x1800053fc  mov     rax, [rbx+108h]
0x180005403  cmp     byte ptr [rax+98h], 0
0x18000540a  jnz     short loc_18000545E
0x18000540c  mov     word ptr [rax+9Ah], 2
0x180005415  jmp     short loc_180005451
0x180005417  lea     rcx, aCommandreasonP; "CommandReason::process_shutdown_ignored"
0x18000541e  mov     al, 43h ; 'C'
0x180005420  mov     r8, rcx
0x180005423  mov     edx, 1
0x180005428  add     rcx, rdx
0x18000542b  cmp     al, 3Ah ; ':'
0x18000542d  jnz     short loc_180005432
0x18000542f  mov     r8, rcx
0x180005432  mov     al, [rcx]
0x180005434  test    al, al
0x180005436  jnz     short loc_180005428
0x180005438  mov     rax, [rbx+108h]
0x18000543f  cmp     byte ptr [rax+98h], 0
0x180005446  jnz     short loc_18000545E
0x180005448  mov     word ptr [rax+9Ah], 4
0x180005451  mov     [rax+98h], dl
0x180005457  mov     [rax+0A0h], r8
0x18000545e  add     rsp, 20h
0x180005462  pop     rbx
0x180005463  retn
```
