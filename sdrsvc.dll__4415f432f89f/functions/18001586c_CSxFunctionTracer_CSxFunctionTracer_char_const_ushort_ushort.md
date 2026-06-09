# CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)

- ea: `0x18001586c`
- end: `0x18001596b`
- name: `??0CSxFunctionTracer@@QEAA@PEBDGG@Z`
- size: `255`
- prototype: `CSxFunctionTracer *__fastcall(CSxFunctionTracer *this, const char *, __int16, __int16)`
- caller_count: `155`
- callee_count: `3`
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

- `0x18000ea7c`
- `0x18000eabc`
- `0x18001586c`

## import_xrefs

- `SXSHARED!SxTracerGetThreadContextRetail` at `0x1800158ac`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x1800158ac`

## pseudocode

```c
CSxFunctionTracer *__fastcall CSxFunctionTracer::CSxFunctionTracer(
        CSxFunctionTracer *this,
        const char *a2,
        __int16 a3,
        __int16 a4)
{
  char *v4; // rdi
  int ThreadContextRetail; // eax
  __int64 v7; // rcx
  _DWORD *v8; // rcx
  __int64 v9; // rdx

  *((_WORD *)this + 2) = a3;
  *(_DWORD *)this = 0;
  v4 = (char *)this + 32;
  *((_WORD *)this + 6) = a4;
  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 3) = 0;
  *((_WORD *)this + 3) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 4) = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)this + 32);
  if ( ThreadContextRetail >= 0 )
  {
    v7 = *(_QWORD *)v4;
    *((_QWORD *)this + 3) = *(_QWORD *)(*(_QWORD *)v4 + 32LL);
    *(_QWORD *)(v7 + 32) = this;
LABEL_6:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_6;
  }
LABEL_7:
  if ( *((_WORD *)this + 6) )
  {
    if ( *((_WORD *)this + 6) == 1 )
    {
      if ( v8 != (_DWORD *)&WPP_GLOBAL_Control && (v8[7] & 0x20000000) != 0 )
      {
        v9 = 12;
        goto LABEL_18;
      }
    }
    else if ( v8 != (_DWORD *)&WPP_GLOBAL_Control && (v8[7] & 0x20000) != 0 )
    {
      v9 = 13;
      goto LABEL_18;
    }
  }
  else if ( v8 != (_DWORD *)&WPP_GLOBAL_Control && (v8[7] & 0x8000000) != 0 )
  {
    v9 = 11;
LABEL_18:
    WPP_SF_s(*((_QWORD *)v8 + 2), v9, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, *((_QWORD *)this + 2));
  }
  return this;
}

```

## disassembly

```asm
0x18001586c  push    rbx
0x18001586e  push    rsi
0x18001586f  push    rdi
0x180015870  push    r14
0x180015872  sub     rsp, 28h
0x180015876  xor     r14d, r14d
0x180015879  mov     [rcx+4], r8w
0x18001587e  mov     [rcx], r14d
0x180015881  lea     rdi, [rcx+20h]
0x180015885  mov     [rcx+0Ch], r9w
0x18001588a  mov     rbx, rcx
0x18001588d  mov     [rcx+10h], rdx
0x180015891  mov     [rcx+18h], r14
0x180015895  mov     [rcx+6], r14w
0x18001589a  mov     [rcx+8], r14d
0x18001589e  mov     [rcx+28h], r14
0x1800158a2  mov     [rcx+30h], r14d
0x1800158a6  mov     rcx, rdi
0x1800158a9  mov     [rdi], r14
0x1800158ac  call    cs:__imp_SxTracerGetThreadContextRetail
0x1800158b2  lea     rsi, WPP_GLOBAL_Control
0x1800158b9  test    eax, eax
0x1800158bb  js      short loc_1800158CE
0x1800158bd  mov     rcx, [rdi]
0x1800158c0  mov     rax, [rcx+20h]
0x1800158c4  mov     [rbx+18h], rax
0x1800158c8  mov     [rcx+20h], rbx
0x1800158cc  jmp     short loc_1800158F8
0x1800158ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158d5  cmp     rcx, rsi
0x1800158d8  jz      short loc_1800158FF
0x1800158da  test    byte ptr [rcx+1Ch], 1
0x1800158de  jz      short loc_1800158FF
0x1800158e0  mov     rcx, [rcx+10h]
0x1800158e4  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x1800158eb  mov     edx, 0Ah
0x1800158f0  mov     r9d, eax
0x1800158f3  call    WPP_SF_d
0x1800158f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158ff  cmp     [rbx+0Ch], r14w
0x180015904  jnz     short loc_18001591B
0x180015906  cmp     rcx, rsi
0x180015909  jz      short loc_18001595E
0x18001590b  test    dword ptr [rcx+1Ch], 8000000h
0x180015912  jz      short loc_18001595E
0x180015914  mov     edx, 0Bh
0x180015919  jmp     short loc_18001594A
0x18001591b  cmp     word ptr [rbx+0Ch], 1
0x180015920  jnz     short loc_180015937
0x180015922  cmp     rcx, rsi
0x180015925  jz      short loc_18001595E
0x180015927  test    dword ptr [rcx+1Ch], 20000000h
0x18001592e  jz      short loc_18001595E
0x180015930  mov     edx, 0Ch
0x180015935  jmp     short loc_18001594A
0x180015937  cmp     rcx, rsi
0x18001593a  jz      short loc_18001595E
0x18001593c  test    dword ptr [rcx+1Ch], 20000h
0x180015943  jz      short loc_18001595E
0x180015945  mov     edx, 0Dh
0x18001594a  mov     r9, [rbx+10h]
0x18001594e  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x180015955  mov     rcx, [rcx+10h]
0x180015959  call    WPP_SF_s
0x18001595e  mov     rax, rbx
0x180015961  add     rsp, 28h
0x180015965  pop     r14
0x180015967  pop     rdi
0x180015968  pop     rsi
0x180015969  pop     rbx
0x18001596a  retn
```
