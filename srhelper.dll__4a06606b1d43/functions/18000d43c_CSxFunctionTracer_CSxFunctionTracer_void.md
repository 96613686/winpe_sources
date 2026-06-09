# CSxFunctionTracer::~CSxFunctionTracer(void)

- ea: `0x18000d43c`
- end: `0x18000d696`
- name: `??1CSxFunctionTracer@@QEAA@XZ`
- size: `602`
- prototype: `void __fastcall(CSxFunctionTracer *this, __int64, __int64)`
- caller_count: `53`
- callee_count: `5`
- tags: ``

## callers

- `0x180002054`
- `0x1800022e4`
- `0x180002658`
- `0x180002818`
- `0x1800029d8`
- `0x180002e9c`
- `0x180003360`
- `0x180003550`
- `0x180003740`
- `0x180003854`
- `0x180003968`
- `0x180003b24`
- `0x18000408c`
- `0x1800044ac`
- `0x180004928`
- `0x180004c2c`
- `0x180004e20`
- `0x1800050dc`
- `0x180005478`
- `0x1800055a4`
- `0x18000572c`
- `0x180005c6c`
- `0x180005e30`
- `0x1800062e8`
- `0x180006840`
- `0x180006b50`
- `0x18000a110`
- `0x18000a3c0`
- `0x18000a500`
- `0x18000a790`
- `0x18000ab80`
- `0x18000af70`
- `0x18000b3b0`
- `0x18000bbe0`
- `0x18000bdd0`
- `0x18000bf70`
- `0x18000c258`
- `0x18000c468`
- `0x18000c6e0`
- `0x18000c890`
- `0x18000ca98`
- `0x18000cc20`
- `0x18000dc78`
- `0x18000dd64`
- `0x18000deac`
- `0x18000e0dc`
- `0x18000e3b8`
- `0x18000e554`
- `0x18000e7ec`
- `0x18000ea60`

## callees

- `0x18000d43c`
- `0x18000da38`
- `0x18000da9c`
- `0x18000db10`
- `0x18000dba0`

## import_xrefs

- `SXSHARED!SxTracerDebuggerBreak` at `0x18000d5a3`
- `SXSHARED!SxTracerDebuggerBreak` at `0x18000d5a3`
- `SXSHARED!SxTracerShouldTrackFailure` at `0x18000d457`
- `SXSHARED!SxTracerShouldTrackFailure` at `0x18000d457`
- `KERNEL32!LocalFree` at `0x18000d4e1`
- `KERNEL32!LocalFree` at `0x18000d657`
- `KERNEL32!LocalFree` at `0x18000d67d`
- `KERNEL32!LocalFree` at `0x18000d4e1`
- `KERNEL32!LocalFree` at `0x18000d657`
- `KERNEL32!LocalFree` at `0x18000d67d`

## pseudocode

```c
void __fastcall CSxFunctionTracer::~CSxFunctionTracer(CSxFunctionTracer *this, __int64 a2, __int64 a3)
{
  int v4; // edx
  int ShouldTrackFailure; // ebp
  int v6; // r8d
  const char *v7; // rcx
  _QWORD *v8; // r10
  void *v9; // rcx
  int v10; // eax
  __int64 v11; // rax
  __int64 i; // rsi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  void *v17; // rcx

  if ( *(int *)this >= 0 )
  {
    if ( *((_WORD *)this + 6) )
    {
      if ( *((_WORD *)this + 6) == 1 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) == 0 )
        {
          goto LABEL_40;
        }
        v14 = 17;
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) == 0 )
        {
          goto LABEL_40;
        }
        v14 = 18;
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
      {
        goto LABEL_40;
      }
      v14 = 16;
    }
    WPP_SF_s(v13[2], v14, a3, *((_QWORD *)this + 2));
    goto LABEL_40;
  }
  ShouldTrackFailure = SxTracerShouldTrackFailure();
  v7 = "FAILED[TRACK]";
  if ( !ShouldTrackFailure )
    v7 = "FAILED";
  if ( !*((_DWORD *)this + 2) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) == 0 )
      goto LABEL_9;
    WPP_SF_sdsdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((unsigned __int16 *)this + 3),
      *((unsigned __int16 *)this + 2),
      *((_QWORD *)this + 2),
      *((_WORD *)this + 2),
      (__int64)v7,
      *((_WORD *)this + 3),
      *(_DWORD *)this);
  }
  v8 = WPP_GLOBAL_Control;
LABEL_9:
  if ( *((_QWORD *)this + 5) )
  {
    v7 = (const char *)*((_QWORD *)this + 4);
    if ( *(_DWORD *)this != *((_DWORD *)v7 + 6) )
    {
      v9 = (void *)*((_QWORD *)v7 + 2);
      if ( v9 )
      {
        LocalFree(v9);
        *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = 0;
      }
      *(_DWORD *)(*((_QWORD *)this + 4) + 4LL) = *((_DWORD *)this + 12);
      *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = *((_QWORD *)this + 5);
      v7 = (const char *)*((_QWORD *)this + 4);
      v10 = *(_DWORD *)this;
      *((_QWORD *)this + 5) = 0;
      *((_DWORD *)v7 + 6) = v10;
      v8 = WPP_GLOBAL_Control;
    }
  }
  v11 = *((_QWORD *)this + 4);
  if ( !v11 || *(_DWORD *)this != *(_DWORD *)(v11 + 8) )
  {
    if ( !*((_DWORD *)this + 2) )
    {
      for ( i = *((_QWORD *)this + 3); i; i = *(_QWORD *)(i + 24) )
      {
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
        {
          WPP_SF_sdd(v8[2], v4, v6, *(_QWORD *)(i + 16), *(_WORD *)(i + 4), *(_DWORD *)i);
          v8 = WPP_GLOBAL_Control;
        }
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
        WPP_SF_sd(
          v8[2],
          25,
          (unsigned int)WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
          *((_QWORD *)this + 2),
          *((_WORD *)this + 3));
    }
    if ( ShouldTrackFailure )
      SxTracerDebuggerBreak(v7);
  }
LABEL_40:
  v15 = *((_QWORD *)this + 4);
  if ( v15 )
  {
    *(_QWORD *)(v15 + 32) = *((_QWORD *)this + 3);
    v16 = *((_QWORD *)this + 4);
    if ( *((_QWORD *)this + 3) )
    {
      *(_DWORD *)(v16 + 8) = *(_DWORD *)this;
    }
    else
    {
      *(_DWORD *)(v16 + 8) = 0;
      LocalFree(*(HLOCAL *)(*((_QWORD *)this + 4) + 16LL));
      *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 4) + 24LL) = 0;
    }
  }
  v17 = (void *)*((_QWORD *)this + 5);
  if ( v17 )
  {
    LocalFree(v17);
    *((_QWORD *)this + 5) = 0;
  }
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18000d43c  push    rbx
0x18000d43e  push    rbp
0x18000d43f  push    rsi
0x18000d440  push    rdi
0x18000d441  push    r14
0x18000d443  sub     rsp, 40h
0x18000d447  mov     rbx, rcx
0x18000d44a  xor     r14d, r14d
0x18000d44d  mov     ecx, [rcx]
0x18000d44f  test    ecx, ecx
0x18000d451  jns     loc_18000D5AE
0x18000d457  call    cs:__imp_SxTracerShouldTrackFailure
0x18000d45d  mov     ebp, eax
0x18000d45f  lea     rcx, aFailedTrack; "FAILED[TRACK]"
0x18000d466  test    ebp, ebp
0x18000d468  lea     rax, aFailed; "FAILED"
0x18000d46f  lea     rdi, WPP_GLOBAL_Control
0x18000d476  cmovz   rcx, rax
0x18000d47a  cmp     [rbx+8], r14d
0x18000d47e  jnz     short loc_18000D4C0
0x18000d480  mov     r10, cs:WPP_GLOBAL_Control
0x18000d487  cmp     r10, rdi
0x18000d48a  jz      short loc_18000D4C7
0x18000d48c  test    dword ptr [r10+1Ch], 2000000h
0x18000d494  jz      short loc_18000D4C7
0x18000d496  movzx   edx, word ptr [rbx+6]
0x18000d49a  mov     eax, [rbx]
0x18000d49c  movzx   r8d, word ptr [rbx+4]
0x18000d4a1  mov     r9, [rbx+10h]
0x18000d4a5  mov     [rsp+68h+var_30], eax
0x18000d4a9  mov     [rsp+68h+var_38], edx
0x18000d4ad  mov     [rsp+68h+var_40], rcx
0x18000d4b2  mov     rcx, [r10+10h]
0x18000d4b6  mov     [rsp+68h+var_48], r8d
0x18000d4bb  call    WPP_SF_sdsdd
0x18000d4c0  mov     r10, cs:WPP_GLOBAL_Control
0x18000d4c7  cmp     [rbx+28h], r14
0x18000d4cb  jz      short loc_18000D519
0x18000d4cd  mov     rcx, [rbx+20h]
0x18000d4d1  mov     eax, [rcx+18h]
0x18000d4d4  cmp     [rbx], eax
0x18000d4d6  jz      short loc_18000D519
0x18000d4d8  mov     rcx, [rcx+10h]; hMem
0x18000d4dc  test    rcx, rcx
0x18000d4df  jz      short loc_18000D4EF
0x18000d4e1  call    cs:__imp_LocalFree
0x18000d4e7  mov     rax, [rbx+20h]
0x18000d4eb  mov     [rax+10h], r14
0x18000d4ef  mov     rcx, [rbx+20h]
0x18000d4f3  mov     eax, [rbx+30h]
0x18000d4f6  mov     [rcx+4], eax
0x18000d4f9  mov     rax, [rbx+28h]
0x18000d4fd  mov     rcx, [rbx+20h]
0x18000d501  mov     [rcx+10h], rax
0x18000d505  mov     rcx, [rbx+20h]
0x18000d509  mov     eax, [rbx]
0x18000d50b  mov     [rbx+28h], r14
0x18000d50f  mov     [rcx+18h], eax
0x18000d512  mov     r10, cs:WPP_GLOBAL_Control
0x18000d519  mov     rax, [rbx+20h]
0x18000d51d  test    rax, rax
0x18000d520  jz      short loc_18000D52D
0x18000d522  mov     eax, [rax+8]
0x18000d525  cmp     [rbx], eax
0x18000d527  jz      loc_18000D630
0x18000d52d  cmp     [rbx+8], r14d
0x18000d531  jnz     short loc_18000D59B
0x18000d533  mov     rsi, [rbx+18h]
0x18000d537  jmp     short loc_18000D56B
0x18000d539  cmp     r10, rdi
0x18000d53c  jz      short loc_18000D567
0x18000d53e  test    byte ptr [r10+1Ch], 1
0x18000d543  jz      short loc_18000D567
0x18000d545  movzx   ecx, word ptr [rsi+4]
0x18000d549  mov     eax, [rsi]
0x18000d54b  mov     r9, [rsi+10h]
0x18000d54f  mov     dword ptr [rsp+68h+var_40], eax
0x18000d553  mov     [rsp+68h+var_48], ecx
0x18000d557  mov     rcx, [r10+10h]
0x18000d55b  call    WPP_SF_sdd
0x18000d560  mov     r10, cs:WPP_GLOBAL_Control
0x18000d567  mov     rsi, [rsi+18h]
0x18000d56b  test    rsi, rsi
0x18000d56e  jnz     short loc_18000D539
0x18000d570  cmp     r10, rdi
0x18000d573  jz      short loc_18000D59B
0x18000d575  test    byte ptr [r10+1Ch], 1
0x18000d57a  jz      short loc_18000D59B
0x18000d57c  movzx   eax, word ptr [rbx+6]
0x18000d580  lea     edx, [rsi+19h]
0x18000d583  mov     r9, [rbx+10h]
0x18000d587  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x18000d58e  mov     rcx, [r10+10h]
0x18000d592  mov     [rsp+68h+var_48], eax
0x18000d596  call    WPP_SF_sd
0x18000d59b  test    ebp, ebp
0x18000d59d  jz      loc_18000D630
0x18000d5a3  call    cs:__imp_SxTracerDebuggerBreak
0x18000d5a9  jmp     loc_18000D630
0x18000d5ae  cmp     [rbx+0Ch], r14w
0x18000d5b3  jnz     short loc_18000D5D8
0x18000d5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5bc  lea     rdi, WPP_GLOBAL_Control
0x18000d5c3  cmp     rcx, rdi
0x18000d5c6  jz      short loc_18000D630
0x18000d5c8  test    dword ptr [rcx+1Ch], 8000000h
0x18000d5cf  jz      short loc_18000D630
0x18000d5d1  mov     edx, 10h
0x18000d5d6  jmp     short loc_18000D623
0x18000d5d8  cmp     word ptr [rbx+0Ch], 1
0x18000d5dd  jnz     short loc_18000D602
0x18000d5df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5e6  lea     rdi, WPP_GLOBAL_Control
0x18000d5ed  cmp     rcx, rdi
0x18000d5f0  jz      short loc_18000D630
0x18000d5f2  test    dword ptr [rcx+1Ch], 20000000h
0x18000d5f9  jz      short loc_18000D630
0x18000d5fb  mov     edx, 11h
0x18000d600  jmp     short loc_18000D623
0x18000d602  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d609  lea     rdi, WPP_GLOBAL_Control
0x18000d610  cmp     rcx, rdi
0x18000d613  jz      short loc_18000D630
0x18000d615  test    dword ptr [rcx+1Ch], 20000h
0x18000d61c  jz      short loc_18000D630
0x18000d61e  mov     edx, 12h
0x18000d623  mov     r9, [rbx+10h]
0x18000d627  mov     rcx, [rcx+10h]
0x18000d62b  call    WPP_SF_s
0x18000d630  mov     rcx, [rbx+20h]
0x18000d634  test    rcx, rcx
0x18000d637  jz      short loc_18000D674
0x18000d639  mov     rax, [rbx+18h]
0x18000d63d  mov     [rcx+20h], rax
0x18000d641  mov     rcx, [rbx+20h]
0x18000d645  cmp     [rbx+18h], r14
0x18000d649  jnz     short loc_18000D66F
0x18000d64b  mov     [rcx+8], r14d
0x18000d64f  mov     rcx, [rbx+20h]
0x18000d653  mov     rcx, [rcx+10h]; hMem
0x18000d657  call    cs:__imp_LocalFree
0x18000d65d  mov     rax, [rbx+20h]
0x18000d661  mov     [rax+10h], r14
0x18000d665  mov     rax, [rbx+20h]
0x18000d669  mov     [rax+18h], r14d
0x18000d66d  jmp     short loc_18000D674
0x18000d66f  mov     eax, [rbx]
0x18000d671  mov     [rcx+8], eax
0x18000d674  mov     rcx, [rbx+28h]; hMem
0x18000d678  test    rcx, rcx
0x18000d67b  jz      short loc_18000D687
0x18000d67d  call    cs:__imp_LocalFree
0x18000d683  mov     [rbx+28h], r14
0x18000d687  mov     [rbx+18h], r14
0x18000d68b  add     rsp, 40h
0x18000d68f  pop     r14
0x18000d691  pop     rdi
0x18000d692  pop     rsi
0x18000d693  pop     rbp
0x18000d694  pop     rbx
0x18000d695  retn
```
