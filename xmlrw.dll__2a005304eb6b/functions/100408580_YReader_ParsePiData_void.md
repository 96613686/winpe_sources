# YReader::ParsePiData(void)

- ea: `0x100408580`
- end: `0x10040874b`
- name: `?ParsePiData@YReader@@AEAAXXZ`
- size: `459`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100403ba0`
- `0x1004083e0`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x100408580`
- `0x100415490`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParsePiData(YReader *this)
{
  int v2; // eax
  int v3; // ecx
  int i; // eax
  int v5; // eax
  signed int v6; // esi
  __int64 v7; // rcx
  int v8; // eax
  void (__fastcall *v9)(Scanner *__hidden); // rax
  void *v10[2]; // [rsp+20h] [rbp-38h] BYREF
  char *v11; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+38h] [rbp-20h]

  v10[0] = 0;
  LODWORD(v10[1]) = 0;
  v11 = 0;
  v12 = 0;
  v2 = 0x7FFFFFFF;
  *((_QWORD *)this + 230) = *(_QWORD *)(*((_QWORD *)this + 55) + 16LL);
  v3 = *((_DWORD *)this + 458);
  if ( v3 > 0 )
    v2 = v3;
  *((_DWORD *)this + 77) = v2;
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  for ( i = *((_DWORD *)this + 28); i == 7; i = *((_DWORD *)this + 28) )
  {
    if ( v10[0] )
    {
      v5 = (int)v10[1];
      if ( LODWORD(v10[1]) > 0x3FFFFFFF
        || (v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13)) + 2 * v5,
            v6 < 0) )
      {
        MXRRaiseException(-2147024882);
        JUMPOUT(0x10040874ALL);
      }
      _mm_lfence();
      v10[0] = BlockAlloc::ReallocData((YReader *)((char *)this + 416), (char *)v10[0], v6);
      v7 = *((_QWORD *)this + 13);
      v11 = (char *)v10[0] + 2 * LODWORD(v10[1]);
      (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v7 + 104LL))(v7, &v11);
      LODWORD(v10[1]) += v12;
    }
    else
    {
      YReader::GetTokenData(this, (struct StringPtr *)v10);
    }
    v8 = *((_DWORD *)this + 78);
    if ( v8 )
    {
      if ( v8 > 0 )
        goto LABEL_20;
    }
    else if ( *((int *)this + 77) <= 0 )
    {
      v9 = (void (__fastcall *)(Scanner *__hidden))*((_QWORD *)this + 27);
      if ( v9 == Scanner::ScanAttributeValue
        || v9 == Scanner::ScanCdSectData
        || v9 == Scanner::ScanCommentData
        || v9 == Scanner::ScanPiData )
      {
        *((_DWORD *)this + 78) = 1;
        goto LABEL_20;
      }
    }
    (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  }
  if ( i != 18 )
  {
    MXRRaiseException(-1072894390);
    __debugbreak();
  }
  *((_QWORD *)this + 230) = *((_QWORD *)this + 202);
LABEL_20:
  *((_OWORD *)this + 102) = *(_OWORD *)v10;
}

```

## disassembly

```asm
0x100408580  mov     [rsp+arg_0], rbx
0x100408585  mov     [rsp+arg_8], rbp
0x10040858a  mov     [rsp+arg_10], rsi
0x10040858f  mov     [rsp+arg_18], rdi
0x100408594  push    r12
0x100408596  push    r14
0x100408598  push    r15
0x10040859a  sub     rsp, 40h
0x10040859e  xor     eax, eax
0x1004085a0  mov     rbx, rcx
0x1004085a3  mov     [rsp+58h+var_38], rax
0x1004085a8  mov     dword ptr [rsp+58h+var_38+8], eax
0x1004085ac  mov     [rsp+58h+var_28], rax
0x1004085b1  mov     [rsp+58h+var_20], eax
0x1004085b5  mov     rax, [rcx+1B8h]
0x1004085bc  mov     rcx, [rax+10h]
0x1004085c0  mov     eax, 7FFFFFFFh
0x1004085c5  mov     [rbx+730h], rcx
0x1004085cc  mov     ecx, [rbx+728h]
0x1004085d2  test    ecx, ecx
0x1004085d4  cmovg   eax, ecx
0x1004085d7  lea     rcx, [rbx+28h]
0x1004085db  mov     [rbx+134h], eax
0x1004085e1  mov     rax, [rbx+0D8h]
0x1004085e8  call    cs:__guard_dispatch_icall_fptr
0x1004085ee  mov     eax, [rbx+70h]
0x1004085f1  cmp     eax, 7
0x1004085f4  jnz     loc_1004086F7
0x1004085fa  lea     rbp, ?ScanAttributeValue@Scanner@@AEAAXXZ; Scanner::ScanAttributeValue(void)
0x100408601  lea     r14, ?ScanCdSectData@Scanner@@AEAAXXZ; Scanner::ScanCdSectData(void)
0x100408608  lea     r15, ?ScanCommentData@Scanner@@AEAAXXZ; Scanner::ScanCommentData(void)
0x10040860f  lea     r12, ?ScanPiData@Scanner@@AEAAXXZ; Scanner::ScanPiData(void)
0x100408616  cmp     [rsp+58h+var_38], 0
0x10040861c  jnz     short loc_10040862D
0x10040861e  lea     rdx, [rsp+58h+var_38]; struct StringPtr *
0x100408623  mov     rcx, rbx; this
0x100408626  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x10040862b  jmp     short loc_10040869F
0x10040862d  mov     eax, dword ptr [rsp+58h+var_38+8]
0x100408631  cmp     eax, 3FFFFFFFh
0x100408636  ja      loc_100408740
0x10040863c  mov     rcx, [rbx+68h]
0x100408640  lea     esi, [rax+rax]
0x100408643  mov     rax, [rcx]
0x100408646  mov     rax, [rax+60h]
0x10040864a  call    cs:__guard_dispatch_icall_fptr
0x100408650  add     esi, eax
0x100408652  js      loc_100408740
0x100408658  lfence
0x10040865b  mov     rdx, [rsp+58h+var_38]; void *
0x100408660  lea     rcx, [rbx+1A0h]; this
0x100408667  mov     r8d, esi; unsigned int
0x10040866a  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x10040866f  mov     ecx, dword ptr [rsp+58h+var_38+8]
0x100408673  lea     rdx, [rsp+58h+var_28]
0x100408678  mov     [rsp+58h+var_38], rax
0x10040867d  lea     rax, [rax+rcx*2]
0x100408681  mov     rcx, [rbx+68h]
0x100408685  mov     [rsp+58h+var_28], rax
0x10040868a  mov     rax, [rcx]
0x10040868d  mov     rax, [rax+68h]
0x100408691  call    cs:__guard_dispatch_icall_fptr
0x100408697  mov     eax, [rsp+58h+var_20]
0x10040869b  add     dword ptr [rsp+58h+var_38+8], eax
0x10040869f  mov     eax, [rbx+138h]
0x1004086a5  test    eax, eax
0x1004086a7  jnz     short loc_1004086D8
0x1004086a9  cmp     [rbx+134h], eax
0x1004086af  jg      short loc_1004086DA
0x1004086b1  mov     rax, [rbx+0D8h]
0x1004086b8  cmp     rax, rbp
0x1004086bb  jz      short loc_1004086CC
0x1004086bd  cmp     rax, r14
0x1004086c0  jz      short loc_1004086CC
0x1004086c2  cmp     rax, r15
0x1004086c5  jz      short loc_1004086CC
0x1004086c7  cmp     rax, r12
0x1004086ca  jnz     short loc_1004086DA
0x1004086cc  mov     dword ptr [rbx+138h], 1
0x1004086d6  jmp     short loc_10040870A
0x1004086d8  jg      short loc_10040870A
0x1004086da  mov     rax, [rbx+0D8h]
0x1004086e1  lea     rcx, [rbx+28h]
0x1004086e5  call    cs:__guard_dispatch_icall_fptr
0x1004086eb  mov     eax, [rbx+70h]
0x1004086ee  cmp     eax, 7
0x1004086f1  jz      loc_100408616
0x1004086f7  cmp     eax, 12h
0x1004086fa  jnz     short loc_100408735
0x1004086fc  mov     rax, [rbx+650h]
0x100408703  mov     [rbx+730h], rax
0x10040870a  movups  xmm0, xmmword ptr [rsp+58h+var_38]
0x10040870f  mov     rbp, [rsp+58h+arg_8]
0x100408714  mov     rsi, [rsp+58h+arg_10]
0x100408719  mov     rdi, [rsp+58h+arg_18]
0x10040871e  movups  xmmword ptr [rbx+660h], xmm0
0x100408725  mov     rbx, [rsp+58h+arg_0]
0x10040872a  add     rsp, 40h
0x10040872e  pop     r15
0x100408730  pop     r14
0x100408732  pop     r12
0x100408734  retn
0x100408735  mov     ecx, 0C00CEE4Ah; int
0x10040873a  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040873f  int     3; Trap to Debugger
0x100408740  mov     ecx, 8007000Eh; int
0x100408745  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
