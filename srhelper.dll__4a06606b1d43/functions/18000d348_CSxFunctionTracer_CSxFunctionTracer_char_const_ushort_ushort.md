# CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)

- ea: `0x18000d348`
- end: `0x18000d434`
- name: `??0CSxFunctionTracer@@QEAA@PEBDGG@Z`
- size: `236`
- prototype: `CSxFunctionTracer *__fastcall(CSxFunctionTracer *this, const char *, __int16)`
- caller_count: `53`
- callee_count: `3`
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

- `0x18000d348`
- `0x18000d9f0`
- `0x18000da38`

## import_xrefs

- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000d388`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000d388`

## pseudocode

```c
CSxFunctionTracer *__fastcall CSxFunctionTracer::CSxFunctionTracer(CSxFunctionTracer *this, const char *a2, __int16 a3)
{
  char *v3; // rdi
  int ThreadContextRetail; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rcx
  _DWORD *v9; // rcx
  __int64 v10; // rdx

  *((_WORD *)this + 2) = a3;
  *(_DWORD *)this = 0;
  v3 = (char *)this + 32;
  *((_WORD *)this + 3) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = a2;
  *((_WORD *)this + 6) = 1;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 4) = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)this + 32);
  if ( ThreadContextRetail >= 0 )
  {
    v8 = *(_QWORD *)v3;
    *((_QWORD *)this + 3) = *(_QWORD *)(*(_QWORD *)v3 + 32LL);
    *(_QWORD *)(v8 + 32) = this;
LABEL_6:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, (unsigned int)ThreadContextRetail);
    goto LABEL_6;
  }
LABEL_7:
  if ( *((_WORD *)this + 6) )
  {
    if ( *((_WORD *)this + 6) == 1 )
    {
      if ( v9 != (_DWORD *)&WPP_GLOBAL_Control && (v9[7] & 0x20000000) != 0 )
      {
        v10 = 12;
        goto LABEL_18;
      }
    }
    else if ( v9 != (_DWORD *)&WPP_GLOBAL_Control && (v9[7] & 0x20000) != 0 )
    {
      v10 = 13;
      goto LABEL_18;
    }
  }
  else if ( v9 != (_DWORD *)&WPP_GLOBAL_Control && (v9[7] & 0x8000000) != 0 )
  {
    v10 = 11;
LABEL_18:
    WPP_SF_s(*((_QWORD *)v9 + 2), v10, v7, *((_QWORD *)this + 2));
  }
  return this;
}

```

## disassembly

```asm
0x18000d348  push    rbx
0x18000d34a  push    rbp
0x18000d34b  push    rsi
0x18000d34c  push    rdi
0x18000d34d  push    r14
0x18000d34f  sub     rsp, 20h
0x18000d353  xor     ebp, ebp
0x18000d355  mov     [rcx+4], r8w
0x18000d35a  mov     [rcx], ebp
0x18000d35c  lea     rdi, [rcx+20h]
0x18000d360  mov     rbx, rcx
0x18000d363  mov     [rcx+6], bp
0x18000d367  mov     [rcx+8], ebp
0x18000d36a  mov     [rcx+10h], rdx
0x18000d36e  lea     r14d, [rbp+1]
0x18000d372  mov     [rcx+0Ch], r14w
0x18000d377  mov     [rcx+18h], rbp
0x18000d37b  mov     [rcx+28h], rbp
0x18000d37f  mov     [rcx+30h], ebp
0x18000d382  mov     rcx, rdi
0x18000d385  mov     [rdi], rbp
0x18000d388  call    cs:__imp_SxTracerGetThreadContextRetail
0x18000d38e  lea     rsi, WPP_GLOBAL_Control
0x18000d395  test    eax, eax
0x18000d397  js      short loc_18000D3AA
0x18000d399  mov     rcx, [rdi]
0x18000d39c  mov     rax, [rcx+20h]
0x18000d3a0  mov     [rbx+18h], rax
0x18000d3a4  mov     [rcx+20h], rbx
0x18000d3a8  jmp     short loc_18000D3C8
0x18000d3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3b1  cmp     rcx, rsi
0x18000d3b4  jz      short loc_18000D3CF
0x18000d3b6  test    [rcx+1Ch], r14b
0x18000d3ba  jz      short loc_18000D3CF
0x18000d3bc  mov     rcx, [rcx+10h]
0x18000d3c0  mov     r9d, eax
0x18000d3c3  call    WPP_SF_d
0x18000d3c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3cf  cmp     [rbx+0Ch], bp
0x18000d3d3  jnz     short loc_18000D3EA
0x18000d3d5  cmp     rcx, rsi
0x18000d3d8  jz      short loc_18000D426
0x18000d3da  test    dword ptr [rcx+1Ch], 8000000h
0x18000d3e1  jz      short loc_18000D426
0x18000d3e3  mov     edx, 0Bh
0x18000d3e8  jmp     short loc_18000D419
0x18000d3ea  cmp     [rbx+0Ch], r14w
0x18000d3ef  jnz     short loc_18000D406
0x18000d3f1  cmp     rcx, rsi
0x18000d3f4  jz      short loc_18000D426
0x18000d3f6  test    dword ptr [rcx+1Ch], 20000000h
0x18000d3fd  jz      short loc_18000D426
0x18000d3ff  mov     edx, 0Ch
0x18000d404  jmp     short loc_18000D419
0x18000d406  cmp     rcx, rsi
0x18000d409  jz      short loc_18000D426
0x18000d40b  test    dword ptr [rcx+1Ch], 20000h
0x18000d412  jz      short loc_18000D426
0x18000d414  mov     edx, 0Dh
0x18000d419  mov     r9, [rbx+10h]
0x18000d41d  mov     rcx, [rcx+10h]
0x18000d421  call    WPP_SF_s
0x18000d426  mov     rax, rbx
0x18000d429  add     rsp, 20h
0x18000d42d  pop     r14
0x18000d42f  pop     rdi
0x18000d430  pop     rsi
0x18000d431  pop     rbp
0x18000d432  pop     rbx
0x18000d433  retn
```
