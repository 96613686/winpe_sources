# CSxFunctionTracer::~CSxFunctionTracer(void)

- ea: `0x180015974`
- end: `0x180015bcb`
- name: `??1CSxFunctionTracer@@QEAA@XZ`
- size: `599`
- prototype: `void __fastcall(CSxFunctionTracer *__hidden this)`
- caller_count: `155`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ac34`
- `0x18000ade0`
- `0x18000b868`
- `0x18000cfb8`
- `0x18000d0a0`
- `0x18000d2bc`
- `0x18000d530`
- `0x18000d5b4`
- `0x18000dffc`
- `0x18000e108`
- `0x18000e420`
- `0x18000e800`
- `0x18000e890`
- `0x18000e900`
- `0x18000ebb0`
- `0x18000edb0`
- `0x18000efb0`
- `0x18000f090`
- `0x18000f230`
- `0x18000f280`
- `0x18000f370`
- `0x18000f7c4`
- `0x18000f85c`
- `0x18000f8d0`
- `0x18000f9d0`
- `0x18000fae0`
- `0x18000fc50`
- `0x18000fda0`
- `0x18000ff90`
- `0x180010080`
- `0x1800101c0`
- `0x180010540`
- `0x180010620`
- `0x1800106f4`
- `0x180010980`
- `0x180010b4c`
- `0x180010c80`
- `0x180011224`
- `0x1800113f0`
- `0x1800114b8`
- `0x1800115dc`
- `0x180011760`
- `0x18001199c`
- `0x180011b84`
- `0x180011cb8`
- `0x180011ec4`
- `0x180011fd4`
- `0x1800120dc`
- `0x1800121bc`
- `0x1800122b8`

## callees

- `0x18000eabc`
- `0x180015974`
- `0x180015d4c`
- `0x180015dcc`
- `0x180015e5c`

## import_xrefs

- `SXSHARED!SxTracerShouldTrackFailure` at `0x18001598f`
- `SXSHARED!SxTracerShouldTrackFailure` at `0x18001598f`
- `SXSHARED!SxTracerDebuggerBreak` at `0x180015ad1`
- `SXSHARED!SxTracerDebuggerBreak` at `0x180015ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015bb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015bb2`

## pseudocode

```c
void __fastcall CSxFunctionTracer::~CSxFunctionTracer(CSxFunctionTracer *this)
{
  int v2; // edx
  int ShouldTrackFailure; // ebp
  int v4; // r8d
  const char *v5; // rcx
  _QWORD *v6; // r10
  void *v7; // rcx
  int v8; // eax
  __int64 v9; // rax
  __int64 i; // rsi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  void *v15; // rcx

  if ( *(int *)this >= 0 )
  {
    if ( *((_WORD *)this + 6) )
    {
      if ( *((_WORD *)this + 6) == 1 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) == 0 )
        {
          goto LABEL_40;
        }
        v12 = 17;
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) == 0 )
        {
          goto LABEL_40;
        }
        v12 = 18;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
      {
        goto LABEL_40;
      }
      v12 = 16;
    }
    WPP_SF_s(v11[2], v12, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, *((_QWORD *)this + 2));
    goto LABEL_40;
  }
  ShouldTrackFailure = SxTracerShouldTrackFailure();
  v5 = "FAILED[TRACK]";
  if ( !ShouldTrackFailure )
    v5 = "FAILED";
  if ( !*((_DWORD *)this + 2) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) == 0 )
      goto LABEL_9;
    WPP_SF_sdsdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((unsigned __int16 *)this + 3),
      *((unsigned __int16 *)this + 2),
      *((_QWORD *)this + 2),
      *((_WORD *)this + 2),
      (__int64)v5,
      *((_WORD *)this + 3),
      *(_DWORD *)this);
  }
  v6 = WPP_GLOBAL_Control;
LABEL_9:
  if ( *((_QWORD *)this + 5) )
  {
    v5 = (const char *)*((_QWORD *)this + 4);
    if ( *(_DWORD *)this != *((_DWORD *)v5 + 6) )
    {
      v7 = (void *)*((_QWORD *)v5 + 2);
      if ( v7 )
      {
        LocalFree(v7);
        *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = 0;
      }
      *(_DWORD *)(*((_QWORD *)this + 4) + 4LL) = *((_DWORD *)this + 12);
      *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = *((_QWORD *)this + 5);
      v5 = (const char *)*((_QWORD *)this + 4);
      v8 = *(_DWORD *)this;
      *((_QWORD *)this + 5) = 0;
      *((_DWORD *)v5 + 6) = v8;
      v6 = WPP_GLOBAL_Control;
    }
  }
  v9 = *((_QWORD *)this + 4);
  if ( !v9 || *(_DWORD *)this != *(_DWORD *)(v9 + 8) )
  {
    if ( !*((_DWORD *)this + 2) )
    {
      for ( i = *((_QWORD *)this + 3); i; i = *(_QWORD *)(i + 24) )
      {
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
        {
          WPP_SF_sdd(v6[2], v2, v4, *(_QWORD *)(i + 16), *(_WORD *)(i + 4), *(_DWORD *)i);
          v6 = WPP_GLOBAL_Control;
        }
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
        WPP_SF_sd(v6[2], v2, v4, *((_QWORD *)this + 2), *((_WORD *)this + 3));
    }
    if ( ShouldTrackFailure )
      SxTracerDebuggerBreak(v5);
  }
LABEL_40:
  v13 = *((_QWORD *)this + 4);
  if ( v13 )
  {
    *(_QWORD *)(v13 + 32) = *((_QWORD *)this + 3);
    v14 = *((_QWORD *)this + 4);
    if ( *((_QWORD *)this + 3) )
    {
      *(_DWORD *)(v14 + 8) = *(_DWORD *)this;
    }
    else
    {
      *(_DWORD *)(v14 + 8) = 0;
      LocalFree(*(HLOCAL *)(*((_QWORD *)this + 4) + 16LL));
      *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 4) + 24LL) = 0;
    }
  }
  v15 = (void *)*((_QWORD *)this + 5);
  if ( v15 )
  {
    LocalFree(v15);
    *((_QWORD *)this + 5) = 0;
  }
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180015974  push    rbx
0x180015976  push    rbp
0x180015977  push    rsi
0x180015978  push    rdi
0x180015979  push    r14
0x18001597b  sub     rsp, 40h
0x18001597f  mov     rbx, rcx
0x180015982  xor     r14d, r14d
0x180015985  mov     ecx, [rcx]
0x180015987  test    ecx, ecx
0x180015989  jns     loc_180015ADC
0x18001598f  call    cs:__imp_SxTracerShouldTrackFailure
0x180015995  mov     ebp, eax
0x180015997  lea     rcx, aFailedTrack; "FAILED[TRACK]"
0x18001599e  test    ebp, ebp
0x1800159a0  lea     rax, aFailed; "FAILED"
0x1800159a7  lea     rdi, WPP_GLOBAL_Control
0x1800159ae  cmovz   rcx, rax
0x1800159b2  cmp     [rbx+8], r14d
0x1800159b6  jnz     short loc_1800159F8
0x1800159b8  mov     r10, cs:WPP_GLOBAL_Control
0x1800159bf  cmp     r10, rdi
0x1800159c2  jz      short loc_1800159FF
0x1800159c4  test    dword ptr [r10+1Ch], 2000000h
0x1800159cc  jz      short loc_1800159FF
0x1800159ce  movzx   edx, word ptr [rbx+6]
0x1800159d2  mov     eax, [rbx]
0x1800159d4  movzx   r8d, word ptr [rbx+4]
0x1800159d9  mov     r9, [rbx+10h]
0x1800159dd  mov     [rsp+68h+var_30], eax
0x1800159e1  mov     [rsp+68h+var_38], edx
0x1800159e5  mov     [rsp+68h+var_40], rcx
0x1800159ea  mov     rcx, [r10+10h]
0x1800159ee  mov     [rsp+68h+var_48], r8d
0x1800159f3  call    WPP_SF_sdsdd
0x1800159f8  mov     r10, cs:WPP_GLOBAL_Control
0x1800159ff  cmp     [rbx+28h], r14
0x180015a03  jz      short loc_180015A51
0x180015a05  mov     rcx, [rbx+20h]
0x180015a09  mov     eax, [rcx+18h]
0x180015a0c  cmp     [rbx], eax
0x180015a0e  jz      short loc_180015A51
0x180015a10  mov     rcx, [rcx+10h]; hMem
0x180015a14  test    rcx, rcx
0x180015a17  jz      short loc_180015A27
0x180015a19  call    cs:__imp_LocalFree
0x180015a1f  mov     rax, [rbx+20h]
0x180015a23  mov     [rax+10h], r14
0x180015a27  mov     rcx, [rbx+20h]
0x180015a2b  mov     eax, [rbx+30h]
0x180015a2e  mov     [rcx+4], eax
0x180015a31  mov     rax, [rbx+28h]
0x180015a35  mov     rcx, [rbx+20h]
0x180015a39  mov     [rcx+10h], rax
0x180015a3d  mov     rcx, [rbx+20h]
0x180015a41  mov     eax, [rbx]
0x180015a43  mov     [rbx+28h], r14
0x180015a47  mov     [rcx+18h], eax
0x180015a4a  mov     r10, cs:WPP_GLOBAL_Control
0x180015a51  mov     rax, [rbx+20h]
0x180015a55  test    rax, rax
0x180015a58  jz      short loc_180015A65
0x180015a5a  mov     eax, [rax+8]
0x180015a5d  cmp     [rbx], eax
0x180015a5f  jz      loc_180015B65
0x180015a65  cmp     [rbx+8], r14d
0x180015a69  jnz     short loc_180015AC9
0x180015a6b  mov     rsi, [rbx+18h]
0x180015a6f  jmp     short loc_180015AA3
0x180015a71  cmp     r10, rdi
0x180015a74  jz      short loc_180015A9F
0x180015a76  test    byte ptr [r10+1Ch], 1
0x180015a7b  jz      short loc_180015A9F
0x180015a7d  movzx   ecx, word ptr [rsi+4]
0x180015a81  mov     eax, [rsi]
0x180015a83  mov     r9, [rsi+10h]
0x180015a87  mov     dword ptr [rsp+68h+var_40], eax
0x180015a8b  mov     [rsp+68h+var_48], ecx
0x180015a8f  mov     rcx, [r10+10h]
0x180015a93  call    WPP_SF_sdd
0x180015a98  mov     r10, cs:WPP_GLOBAL_Control
0x180015a9f  mov     rsi, [rsi+18h]
0x180015aa3  test    rsi, rsi
0x180015aa6  jnz     short loc_180015A71
0x180015aa8  cmp     r10, rdi
0x180015aab  jz      short loc_180015AC9
0x180015aad  test    byte ptr [r10+1Ch], 1
0x180015ab2  jz      short loc_180015AC9
0x180015ab4  movzx   eax, word ptr [rbx+6]
0x180015ab8  mov     r9, [rbx+10h]
0x180015abc  mov     rcx, [r10+10h]
0x180015ac0  mov     [rsp+68h+var_48], eax
0x180015ac4  call    WPP_SF_sd
0x180015ac9  test    ebp, ebp
0x180015acb  jz      loc_180015B65
0x180015ad1  call    cs:__imp_SxTracerDebuggerBreak
0x180015ad7  jmp     loc_180015B65
0x180015adc  cmp     [rbx+0Ch], r14w
0x180015ae1  jnz     short loc_180015B06
0x180015ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180015aea  lea     rdi, WPP_GLOBAL_Control
0x180015af1  cmp     rcx, rdi
0x180015af4  jz      short loc_180015B65
0x180015af6  test    dword ptr [rcx+1Ch], 8000000h
0x180015afd  jz      short loc_180015B65
0x180015aff  mov     edx, 10h
0x180015b04  jmp     short loc_180015B51
0x180015b06  cmp     word ptr [rbx+0Ch], 1
0x180015b0b  jnz     short loc_180015B30
0x180015b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b14  lea     rdi, WPP_GLOBAL_Control
0x180015b1b  cmp     rcx, rdi
0x180015b1e  jz      short loc_180015B65
0x180015b20  test    dword ptr [rcx+1Ch], 20000000h
0x180015b27  jz      short loc_180015B65
0x180015b29  mov     edx, 11h
0x180015b2e  jmp     short loc_180015B51
0x180015b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b37  lea     rdi, WPP_GLOBAL_Control
0x180015b3e  cmp     rcx, rdi
0x180015b41  jz      short loc_180015B65
0x180015b43  test    dword ptr [rcx+1Ch], 20000h
0x180015b4a  jz      short loc_180015B65
0x180015b4c  mov     edx, 12h
0x180015b51  mov     r9, [rbx+10h]
0x180015b55  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x180015b5c  mov     rcx, [rcx+10h]
0x180015b60  call    WPP_SF_s
0x180015b65  mov     rcx, [rbx+20h]
0x180015b69  test    rcx, rcx
0x180015b6c  jz      short loc_180015BA9
0x180015b6e  mov     rax, [rbx+18h]
0x180015b72  mov     [rcx+20h], rax
0x180015b76  mov     rcx, [rbx+20h]
0x180015b7a  cmp     [rbx+18h], r14
0x180015b7e  jnz     short loc_180015BA4
0x180015b80  mov     [rcx+8], r14d
0x180015b84  mov     rcx, [rbx+20h]
0x180015b88  mov     rcx, [rcx+10h]; hMem
0x180015b8c  call    cs:__imp_LocalFree
0x180015b92  mov     rax, [rbx+20h]
0x180015b96  mov     [rax+10h], r14
0x180015b9a  mov     rax, [rbx+20h]
0x180015b9e  mov     [rax+18h], r14d
0x180015ba2  jmp     short loc_180015BA9
0x180015ba4  mov     eax, [rbx]
0x180015ba6  mov     [rcx+8], eax
0x180015ba9  mov     rcx, [rbx+28h]; hMem
0x180015bad  test    rcx, rcx
0x180015bb0  jz      short loc_180015BBC
0x180015bb2  call    cs:__imp_LocalFree
0x180015bb8  mov     [rbx+28h], r14
0x180015bbc  mov     [rbx+18h], r14
0x180015bc0  add     rsp, 40h
0x180015bc4  pop     r14
0x180015bc6  pop     rdi
0x180015bc7  pop     rsi
0x180015bc8  pop     rbp
0x180015bc9  pop     rbx
0x180015bca  retn
```
