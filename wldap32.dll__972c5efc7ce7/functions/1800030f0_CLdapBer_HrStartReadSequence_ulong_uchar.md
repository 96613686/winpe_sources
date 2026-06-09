# CLdapBer::HrStartReadSequence(ulong,uchar)

- ea: `0x1800030f0`
- end: `0x1800032c6`
- name: `?HrStartReadSequence@CLdapBer@@QEAAKKE@Z`
- size: `470`
- prototype: `unsigned int __fastcall(CLdapBer *__hidden this, unsigned int, unsigned __int8)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x1800018d0`
- `0x180002770`
- `0x180003840`
- `0x180012ab0`
- `0x18001ba9c`
- `0x180031128`
- `0x180041e40`
- `0x1800442b0`
- `0x18004459c`
- `0x180046038`
- `0x18004a6c4`

## callees

- `0x1800030f0`
- `0x180003570`
- `0x1800037a8`
- `0x180027530`

## string_xrefs

- `0x180003225`: `HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n`
- `0x180003254`: `HrStartReadSequence expected tag of 0x%x, received 0x%x.\n`
- `0x18000327f`: `HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CLdapBer::HrStartReadSequence(CLdapBer *this, unsigned int a2, char a3)
{
  unsigned int v3; // r10d
  __int64 v5; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  int v9; // r9d
  char v10; // dl
  __int64 v11; // rax
  unsigned int *v12; // rsi
  int v13; // edx
  int v14; // ecx
  unsigned int Length; // r10d
  unsigned int v17; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v18; // [rsp+58h] [rbp+20h] BYREF

  v3 = *(_DWORD *)this;
  v5 = *((unsigned int *)this + 1);
  if ( *(_DWORD *)this > (unsigned int)v5 )
  {
    if ( a3 || (v7 = *(unsigned __int8 *)(v5 + *((_QWORD *)this + 2)), (_DWORD)v7 == a2) )
    {
      v8 = (unsigned int)(v5 + 1);
      *((_DWORD *)this + 1) = v8;
      if ( v3 > (unsigned int)v8 )
      {
        v9 = 1;
        v10 = *(_BYTE *)(v8 + *((_QWORD *)this + 2));
        if ( v10 < 0 )
          v9 = (v10 & 0x7F) + 1;
        v11 = *((unsigned int *)this + 8);
        if ( (unsigned int)v11 >= 0x32 )
        {
          Length = -2147024882;
        }
        else
        {
          v12 = (unsigned int *)((char *)this + 836);
          v13 = *((_DWORD *)this + 209);
          v14 = *((_DWORD *)this + 210);
          *((_DWORD *)this + 4 * v11 + 9) = v8;
          *((_DWORD *)this + 4 * *((unsigned int *)this + 8) + 10) = v9;
          *((_DWORD *)this + 4 * *((unsigned int *)this + 8) + 11) = v14;
          *((_DWORD *)this + 4 * (unsigned int)(*((_DWORD *)this + 8))++ + 12) = v13;
          Length = CLdapBer::HrGetLength(this, v12);
          if ( Length )
            CLdapBer::HrPopSeqStack(this, &v18, &v17, (unsigned int *)this + 210, v12);
          else
            *((_DWORD *)this + 210) = *((_DWORD *)this + 1);
        }
        if ( *((_DWORD *)this + 1) > *(_DWORD *)this )
          return (unsigned int)-2147024809;
        return Length;
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
        LDAPClientPrint(
          0x2000,
          "HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n",
          v3,
          (unsigned int)v8);
    }
    else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
    {
      LDAPClientPrint(0x2000, "HrStartReadSequence expected tag of 0x%x, received 0x%x.\n", a2, v7);
    }
    return 2147942487LL;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
    LDAPClientPrint(0x2000, "HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n", v3, v5);
  return 16;
}

```

## disassembly

```asm
0x1800030f0  push    rbx
0x1800030f2  sub     rsp, 30h
0x1800030f6  mov     r10d, [rcx]
0x1800030f9  movzx   eax, r8b
0x1800030fd  mov     r8d, [rcx+4]
0x180003101  mov     rbx, rcx
0x180003104  cmp     r10d, r8d
0x180003107  jbe     loc_1800031E2
0x18000310d  test    al, al
0x18000310f  jnz     short loc_180003123
0x180003111  mov     rax, [rcx+10h]
0x180003115  movzx   r9d, byte ptr [r8+rax]
0x18000311a  cmp     r9d, edx
0x18000311d  jnz     loc_1800031F7
0x180003123  inc     r8d
0x180003126  mov     [rcx+4], r8d
0x18000312a  cmp     r10d, r8d
0x18000312d  jbe     loc_18000325D
0x180003133  mov     rax, [rcx+10h]
0x180003137  mov     r9d, 1
0x18000313d  mov     [rsp+38h+arg_8], rsi
0x180003142  mov     [rsp+38h+arg_10], rdi
0x180003147  movzx   edx, byte ptr [r8+rax]
0x18000314c  mov     eax, edx
0x18000314e  and     eax, 7Fh
0x180003151  inc     eax
0x180003153  test    dl, dl
0x180003155  cmovs   r9d, eax
0x180003159  mov     eax, [rcx+20h]
0x18000315c  cmp     eax, 32h ; '2'
0x18000315f  jnb     loc_1800032BB
0x180003165  add     rax, rax
0x180003168  lea     rsi, [rcx+344h]
0x18000316f  mov     edx, [rsi]
0x180003171  mov     ecx, [rcx+348h]
0x180003177  mov     [rbx+rax*8+24h], r8d
0x18000317c  mov     eax, [rbx+20h]
0x18000317f  add     rax, rax
0x180003182  mov     [rbx+rax*8+28h], r9d
0x180003187  mov     eax, [rbx+20h]
0x18000318a  add     rax, rax
0x18000318d  mov     [rbx+rax*8+2Ch], ecx
0x180003191  mov     rcx, rbx; this
0x180003194  mov     eax, [rbx+20h]
0x180003197  add     rax, 3
0x18000319b  add     rax, rax
0x18000319e  mov     [rbx+rax*8], edx
0x1800031a1  mov     rdx, rsi; unsigned int *
0x1800031a4  inc     dword ptr [rbx+20h]
0x1800031a7  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x1800031ac  mov     r10d, eax
0x1800031af  test    eax, eax
0x1800031b1  jnz     loc_180003298
0x1800031b7  mov     eax, [rbx+4]
0x1800031ba  mov     [rbx+348h], eax
0x1800031c0  mov     ecx, [rbx]
0x1800031c2  mov     eax, 80070057h
0x1800031c7  cmp     [rbx+4], ecx
0x1800031ca  mov     rdi, [rsp+38h+arg_10]
0x1800031cf  mov     rsi, [rsp+38h+arg_8]
0x1800031d4  cmova   r10d, eax
0x1800031d8  mov     eax, r10d
0x1800031db  add     rsp, 30h
0x1800031df  pop     rbx
0x1800031e0  retn
0x1800031e2  cmp     cs:g_fTracingOn, 0
0x1800031e9  jnz     short loc_18000320C
0x1800031eb  mov     eax, 10h
0x1800031f0  add     rsp, 30h
0x1800031f4  pop     rbx
0x1800031f5  retn
0x1800031f7  cmp     cs:g_fTracingOn, 0
0x1800031fe  jnz     short loc_18000323B
0x180003200  mov     eax, 80070057h
0x180003205  add     rsp, 30h
0x180003209  pop     rbx
0x18000320a  retn
0x18000320c  cmp     cs:g_fProviderEnabled, 0
0x180003213  jz      short loc_1800031EB
0x180003215  test    cs:g_ulTraceFlags, 2000h
0x180003220  jz      short loc_1800031EB
0x180003222  mov     r9d, r8d
0x180003225  lea     rdx, aHrstartreadseq_0; "HrStartReadSequence ran out of data, le"...
0x18000322c  mov     r8d, r10d
0x18000322f  mov     ecx, 2000h
0x180003234  call    LDAPClientPrint
0x180003239  jmp     short loc_1800031EB
0x18000323b  cmp     cs:g_fProviderEnabled, 0
0x180003242  jz      short loc_180003200
0x180003244  test    cs:g_ulTraceFlags, 2000h
0x18000324f  jz      short loc_180003200
0x180003251  mov     r8d, edx
0x180003254  lea     rdx, aHrstartreadseq; "HrStartReadSequence expected tag of 0x%"...
0x18000325b  jmp     short loc_180003289
0x18000325d  cmp     cs:g_fTracingOn, 0
0x180003264  jz      short loc_180003200
0x180003266  cmp     cs:g_fProviderEnabled, 0
0x18000326d  jz      short loc_180003200
0x18000326f  test    cs:g_ulTraceFlags, 2000h
0x18000327a  jz      short loc_180003200
0x18000327c  mov     r9d, r8d
0x18000327f  lea     rdx, aHrstartreadseq_1; "HrStartReadSequence 2 ran out of data, "...
0x180003286  mov     r8d, r10d
0x180003289  mov     ecx, 2000h
0x18000328e  call    LDAPClientPrint
0x180003293  jmp     loc_180003200
0x180003298  lea     r9, [rbx+348h]; unsigned int *
0x18000329f  mov     [rsp+38h+var_18], rsi; unsigned int *
0x1800032a4  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x1800032a9  mov     rcx, rbx; this
0x1800032ac  lea     rdx, [rsp+38h+arg_18]; unsigned int *
0x1800032b1  call    ?HrPopSeqStack@CLdapBer@@AEAAKPEAK000@Z; CLdapBer::HrPopSeqStack(ulong *,ulong *,ulong *,ulong *)
0x1800032b6  jmp     loc_1800031C0
0x1800032bb  mov     r10d, 8007000Eh
0x1800032c1  jmp     loc_1800031C0
```
