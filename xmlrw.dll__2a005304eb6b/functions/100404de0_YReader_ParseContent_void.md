# YReader::ParseContent(void)

- ea: `0x100404de0`
- end: `0x100405109`
- name: `?ParseContent@YReader@@AEAAXXZ`
- size: `809`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x100407b90`
- `0x100407c40`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x100404900`
- `0x100404a40`
- `0x100404c10`
- `0x100404de0`
- `0x100407ec0`
- `0x1004083e0`
- `0x10040aa00`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseContent(YReader *this)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rax
  int v5; // ecx
  __int64 v6; // rdi
  unsigned int v7; // eax
  __int128 v8; // [rsp+20h] [rbp-18h]

  v1 = *((_QWORD *)this + 230);
  v3 = (_QWORD *)*((_QWORD *)this + 55);
  if ( (unsigned __int64)v3 >= v1 || v1 > v3[2] )
  {
    v3 = (_QWORD *)*v3;
    *((_QWORD *)this + 55) = v3;
    if ( !v3 )
    {
LABEL_31:
      MXRRaiseException(-2147467259);
      __debugbreak();
    }
    while ( (unsigned __int64)v3 >= v1 || v1 > v3[3] )
    {
      v4 = (_QWORD *)*v3;
      *((_QWORD *)this + 55) = *v3;
      v3 = v4;
      if ( !v4 )
        goto LABEL_31;
    }
  }
  v3[2] = v1;
  v5 = 0x7FFFFFFF;
  if ( *((int *)this + 458) > 0 )
    v5 = *((_DWORD *)this + 458);
  *((_DWORD *)this + 77) = v5;
  while ( 2 )
  {
    (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
    switch ( *((_DWORD *)this + 28) )
    {
      case 3:
        (*((void (__fastcall **)(char *))this + 192))((char *)this + *((int *)this + 386));
        return;
      case 4:
        YReader::GetTokenData(this, (YReader *)((char *)this + 1568));
        v6 = *((_QWORD *)this + 349);
        v7 = *((_DWORD *)this + 394);
        if ( v7 != *(_DWORD *)(v6 + 8) || memcmp(*((const void **)this + 196), *(const void **)v6, 2LL * v7) )
        {
          MXRRaiseException(-1072894405);
          __debugbreak();
        }
        if ( *(_DWORD *)(v6 + 48) )
        {
          MXRRaiseException(-1072894394);
          __debugbreak();
        }
        *((_DWORD *)this + 444) = 3;
        *(_QWORD *)&v8 = YReader::ParseEmptyElement;
        DWORD2(v8) = 0;
        *((_OWORD *)this + 100) = *(_OWORD *)(v6 + 16);
        *((_OWORD *)this + 101) = *(_OWORD *)(v6 + 32);
        *((_OWORD *)this + 94) = v8;
        return;
      case 7:
        *((_BYTE *)this + 1784) = 0;
        goto LABEL_25;
      case 8:
LABEL_25:
        YReader::GetTokenData(this, (YReader *)((char *)this + 1632));
        *((_DWORD *)this + 444) = (*((_BYTE *)this + 1784) != 0) + 5;
        return;
      case 0xA:
        YReader::ParseCharRef(this);
        return;
      case 0xB:
        if ( YReader::ParseEntityRef(this) )
          continue;
        return;
      case 0xD:
        YReader::ParseCdSect(this);
        return;
      case 0xF:
        YReader::ParseComment(this);
        goto LABEL_29;
      case 0x11:
        YReader::ParsePi(this);
LABEL_29:
        *((_BYTE *)this + 1784) = 1;
        return;
      case 0x3B:
        if ( !*((_BYTE *)this + 1790) || *((_DWORD *)this + 472) != 1 || *((_DWORD *)this + 118) != 1 )
        {
          YReader::HandleEntityEnd(this, **((void ***)this + 349));
          --*(_DWORD *)(*((_QWORD *)this + 349) + 48LL);
          continue;
        }
        *(_QWORD *)&v8 = YReader::ParseDocumentEnd;
        DWORD2(v8) = 0;
        *((_DWORD *)this + 445) = 1;
        *((_DWORD *)this + 444) = 0;
        *((_OWORD *)this + 94) = v8;
        return;
      default:
        return;
    }
  }
}

```

## disassembly

```asm
0x100404de0  push    rbx
0x100404de2  sub     rsp, 30h
0x100404de6  mov     rdx, [rcx+730h]
0x100404ded  mov     rbx, rcx
0x100404df0  mov     rcx, [rcx+1B8h]
0x100404df7  cmp     rcx, rdx
0x100404dfa  jnb     short loc_100404E02
0x100404dfc  cmp     rdx, [rcx+10h]
0x100404e00  jbe     short loc_100404E38
0x100404e02  mov     rcx, [rcx]
0x100404e05  mov     [rbx+1B8h], rcx
0x100404e0c  test    rcx, rcx
0x100404e0f  jz      loc_100405080
0x100404e15  cmp     rcx, rdx
0x100404e18  jnb     short loc_100404E20
0x100404e1a  cmp     rdx, [rcx+18h]
0x100404e1e  jbe     short loc_100404E38
0x100404e20  mov     rax, [rcx]
0x100404e23  mov     [rbx+1B8h], rax
0x100404e2a  mov     rcx, rax
0x100404e2d  test    rax, rax
0x100404e30  jz      loc_100405080
0x100404e36  jmp     short loc_100404E15
0x100404e38  mov     [rcx+10h], rdx
0x100404e3c  mov     ecx, 7FFFFFFFh
0x100404e41  mov     eax, [rbx+728h]
0x100404e47  test    eax, eax
0x100404e49  mov     [rsp+38h+arg_0], rsi
0x100404e4e  lea     rsi, __ImageBase
0x100404e55  cmovg   ecx, eax
0x100404e58  mov     [rsp+38h+arg_8], rdi
0x100404e5d  mov     [rbx+134h], ecx
0x100404e63  mov     rax, [rbx+0D8h]
0x100404e6a  lea     rcx, [rbx+28h]
0x100404e6e  call    cs:__guard_dispatch_icall_fptr
0x100404e74  mov     eax, [rbx+70h]
0x100404e77  add     eax, 0FFFFFFFDh; switch 57 cases
0x100404e7a  cmp     eax, 38h
0x100404e7d  ja      def_100404E97; jumptable 0000000100404E97 default case, cases 5,6,9,12,14,16,18-58
0x100404e83  cdqe
0x100404e85  movzx   eax, ds:(byte_1004050D0 - 100400000h)[rsi+rax]
0x100404e8d  mov     ecx, ds:(jpt_100404E97 - 100400000h)[rsi+rax*4]
0x100404e94  add     rcx, rsi
0x100404e97  jmp     rcx; switch jump
0x100404e99  mov     rcx, rbx; jumptable 0000000100404E97 case 11
0x100404e9c  call    ?ParseEntityRef@YReader@@AEAA_NXZ; YReader::ParseEntityRef(void)
0x100404ea1  test    al, al
0x100404ea3  jnz     short loc_100404E63
0x100404ea5  mov     rsi, [rsp+38h+arg_0]
0x100404eaa  mov     rdi, [rsp+38h+arg_8]
0x100404eaf  add     rsp, 30h
0x100404eb3  pop     rbx
0x100404eb4  retn
0x100404eb5  cmp     byte ptr [rbx+6FEh], 0; jumptable 0000000100404E97 case 59
0x100404ebc  jz      short loc_100404ED0
0x100404ebe  cmp     dword ptr [rbx+760h], 1
0x100404ec5  jnz     short loc_100404ED0
0x100404ec7  cmp     dword ptr [rbx+1D8h], 1
0x100404ece  jz      short loc_100404EF1
0x100404ed0  mov     rdx, [rbx+0AE8h]
0x100404ed7  mov     rcx, rbx; this
0x100404eda  mov     rdx, [rdx]; void *
0x100404edd  call    ?HandleEntityEnd@YReader@@AEAAPEAVDeclEntity@@PEAX@Z; YReader::HandleEntityEnd(void *)
0x100404ee2  mov     rax, [rbx+0AE8h]
0x100404ee9  dec     dword ptr [rax+30h]
0x100404eec  jmp     loc_100404E63
0x100404ef1  mov     rsi, [rsp+38h+arg_0]
0x100404ef6  lea     rcx, ?ParseDocumentEnd@YReader@@AEAAXXZ; YReader::ParseDocumentEnd(void)
0x100404efd  mov     rdi, [rsp+38h+arg_8]
0x100404f02  xor     eax, eax
0x100404f04  mov     qword ptr [rsp+38h+var_18], rcx
0x100404f09  mov     dword ptr [rsp+38h+var_18+8], eax
0x100404f0d  movups  xmm0, [rsp+38h+var_18]
0x100404f12  mov     dword ptr [rbx+6F4h], 1
0x100404f1c  mov     [rbx+6F0h], eax
0x100404f22  movups  xmmword ptr [rbx+5E0h], xmm0
0x100404f29  add     rsp, 30h
0x100404f2d  pop     rbx
0x100404f2e  retn
0x100404f2f  movsxd  rcx, dword ptr [rbx+608h]; jumptable 0000000100404E97 case 3
0x100404f36  mov     rax, [rbx+600h]
0x100404f3d  add     rcx, rbx
0x100404f40  mov     rsi, [rsp+38h+arg_0]
0x100404f45  mov     rdi, [rsp+38h+arg_8]
0x100404f4a  add     rsp, 30h
0x100404f4e  pop     rbx
0x100404f4f  jmp     cs:__guard_dispatch_icall_fptr
0x100404f56  lea     rdx, [rbx+620h]; jumptable 0000000100404E97 case 4
0x100404f5d  mov     rcx, rbx; this
0x100404f60  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100404f65  mov     rdi, [rbx+0AE8h]
0x100404f6c  mov     eax, [rbx+628h]
0x100404f72  cmp     eax, [rdi+8]
0x100404f75  jnz     loc_100405096
0x100404f7b  mov     rdx, [rdi]; Buf2
0x100404f7e  mov     r8d, eax
0x100404f81  mov     rcx, [rbx+620h]; Buf1
0x100404f88  add     r8, r8; Size
0x100404f8b  call    memcmp
0x100404f90  test    eax, eax
0x100404f92  jnz     loc_100405096
0x100404f98  cmp     [rdi+30h], eax
0x100404f9b  jnz     loc_10040508B
0x100404fa1  mov     rsi, [rsp+38h+arg_0]
0x100404fa6  lea     rax, ?ParseEmptyElement@YReader@@AEAAXXZ; YReader::ParseEmptyElement(void)
0x100404fad  mov     dword ptr [rbx+6F0h], 3
0x100404fb7  movups  xmm0, xmmword ptr [rdi+10h]
0x100404fbb  mov     qword ptr [rsp+38h+var_18], rax
0x100404fc0  xor     eax, eax
0x100404fc2  mov     dword ptr [rsp+38h+var_18+8], eax
0x100404fc6  movups  xmmword ptr [rbx+640h], xmm0
0x100404fcd  movups  xmm0, xmmword ptr [rdi+20h]
0x100404fd1  mov     rdi, [rsp+38h+arg_8]
0x100404fd6  movups  xmmword ptr [rbx+650h], xmm0
0x100404fdd  movups  xmm0, [rsp+38h+var_18]
0x100404fe2  movups  xmmword ptr [rbx+5E0h], xmm0
0x100404fe9  add     rsp, 30h
0x100404fed  pop     rbx
0x100404fee  retn
0x100404fef  mov     byte ptr [rbx+6F8h], 0; jumptable 0000000100404E97 case 7
0x100404ff6  lea     rdx, [rbx+660h]; jumptable 0000000100404E97 case 8
0x100404ffd  mov     rcx, rbx; this
0x100405000  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100405005  mov     rsi, [rsp+38h+arg_0]
0x10040500a  xor     eax, eax
0x10040500c  cmp     [rbx+6F8h], al
0x100405012  mov     rdi, [rsp+38h+arg_8]
0x100405017  setnz   al
0x10040501a  add     eax, 5
0x10040501d  mov     [rbx+6F0h], eax
0x100405023  add     rsp, 30h
0x100405027  pop     rbx
0x100405028  retn
0x100405029  mov     rcx, rbx; jumptable 0000000100404E97 case 10
0x10040502c  mov     rsi, [rsp+38h+arg_0]
0x100405031  mov     rdi, [rsp+38h+arg_8]
0x100405036  add     rsp, 30h
0x10040503a  pop     rbx
0x10040503b  jmp     ?ParseCharRef@YReader@@AEAAXXZ; YReader::ParseCharRef(void)
0x100405040  mov     rcx, rbx; jumptable 0000000100404E97 case 13
0x100405043  mov     rsi, [rsp+38h+arg_0]
0x100405048  mov     rdi, [rsp+38h+arg_8]
0x10040504d  add     rsp, 30h
0x100405051  pop     rbx
0x100405052  jmp     ?ParseCdSect@YReader@@AEAAXXZ; YReader::ParseCdSect(void)
0x100405057  mov     rcx, rbx; jumptable 0000000100404E97 case 15
0x10040505a  call    ?ParseComment@YReader@@AEAAXXZ; YReader::ParseComment(void)
0x10040505f  mov     byte ptr [rbx+6F8h], 1
0x100405066  mov     rsi, [rsp+38h+arg_0]; jumptable 0000000100404E97 default case, cases 5,6,9,12,14,16,18-58
0x10040506b  mov     rdi, [rsp+38h+arg_8]
0x100405070  add     rsp, 30h
0x100405074  pop     rbx
0x100405075  retn
0x100405076  mov     rcx, rbx; jumptable 0000000100404E97 case 17
0x100405079  call    ?ParsePi@YReader@@AEAAXXZ; YReader::ParsePi(void)
0x10040507e  jmp     short loc_10040505F
0x100405080  mov     ecx, 80004005h; int
0x100405085  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040508a  int     3; Trap to Debugger
0x10040508b  mov     ecx, 0C00CEE46h; int
0x100405090  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405095  int     3; Trap to Debugger
0x100405096  mov     ecx, 0C00CEE3Bh; int
0x10040509b  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004050a0  int     3; Trap to Debugger
```
