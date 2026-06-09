# YReader::ParseEpilog(void)

- ea: `0x1004081e0`
- end: `0x1004083b5`
- name: `?ParseEpilog@YReader@@AEAAXXZ`
- size: `469`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x100401780`
- `0x100404c10`
- `0x1004081e0`
- `0x1004083e0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseEpilog(YReader *this)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  int v5; // eax
  unsigned int v6; // eax
  int v7; // ecx
  __int128 v8; // [rsp+20h] [rbp-18h]

  v1 = *((_QWORD *)this + 230);
  v3 = (_QWORD *)*((_QWORD *)this + 55);
  if ( (unsigned __int64)v3 >= v1 || v1 > v3[2] )
  {
    v3 = (_QWORD *)*v3;
    *((_QWORD *)this + 55) = v3;
    if ( !v3 )
    {
LABEL_19:
      MXRRaiseException(-2147467259);
      __debugbreak();
    }
    while ( (unsigned __int64)v3 >= v1 || v1 > v3[3] )
    {
      v4 = (_QWORD *)*v3;
      *((_QWORD *)this + 55) = *v3;
      v3 = v4;
      if ( !v4 )
        goto LABEL_19;
    }
  }
  v3[2] = v1;
  v5 = 0x7FFFFFFF;
  if ( *((int *)this + 458) > 0 )
    v5 = *((_DWORD *)this + 458);
  *((_DWORD *)this + 77) = v5;
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  v6 = *((_DWORD *)this + 28) - 3;
  while ( 2 )
  {
    switch ( v6 )
    {
      case 4u:
        MXRRaiseException(-1072894419);
        __debugbreak();
      case 5u:
        v7 = 0x7FFFFFFF;
        if ( *((int *)this + 458) > 0 )
          v7 = *((_DWORD *)this + 458);
        *((_DWORD *)this + 77) = v7;
        (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
        v6 = *((_DWORD *)this + 28) - 3;
        if ( v6 <= 0x38 )
          continue;
        goto LABEL_20;
      case 0xCu:
        YReader::ParseComment(this);
        return;
      case 0xEu:
        YReader::ParsePi(this);
        return;
      case 0x38u:
        *(_QWORD *)&v8 = YReader::ParseDocumentEnd;
        DWORD2(v8) = 0;
        *((_DWORD *)this + 445) = 1;
        *((_DWORD *)this + 444) = 0;
        *((_OWORD *)this + 94) = v8;
        return;
      default:
LABEL_20:
        MXRRaiseException(-1072894406);
        __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x1004081e0  push    rbx
0x1004081e2  sub     rsp, 30h
0x1004081e6  mov     rdx, [rcx+730h]
0x1004081ed  mov     rbx, rcx
0x1004081f0  mov     rax, [rcx+1B8h]
0x1004081f7  cmp     rax, rdx
0x1004081fa  jnb     short loc_100408202
0x1004081fc  cmp     rdx, [rax+10h]
0x100408200  jbe     short loc_100408238
0x100408202  mov     rax, [rax]
0x100408205  mov     [rcx+1B8h], rax
0x10040820c  test    rax, rax
0x10040820f  jz      loc_10040833D
0x100408215  cmp     rax, rdx
0x100408218  jnb     short loc_100408220
0x10040821a  cmp     rdx, [rax+18h]
0x10040821e  jbe     short loc_100408238
0x100408220  mov     rcx, [rax]
0x100408223  mov     [rbx+1B8h], rcx
0x10040822a  mov     rax, rcx
0x10040822d  test    rcx, rcx
0x100408230  jz      loc_10040833D
0x100408236  jmp     short loc_100408215
0x100408238  mov     [rax+10h], rdx
0x10040823c  mov     eax, 7FFFFFFFh
0x100408241  mov     ecx, [rbx+728h]
0x100408247  test    ecx, ecx
0x100408249  mov     [rsp+38h+arg_0], rsi
0x10040824e  cmovg   eax, ecx
0x100408251  mov     [rsp+38h+arg_8], rdi
0x100408256  mov     [rbx+134h], eax
0x10040825c  lea     rcx, [rbx+28h]
0x100408260  mov     rax, [rbx+0D8h]
0x100408267  call    cs:__guard_dispatch_icall_fptr
0x10040826d  mov     eax, [rbx+70h]
0x100408270  sub     eax, 3; switch 57 cases
0x100408273  cmp     eax, 38h
0x100408276  ja      def_100408297; jumptable 0000000100408297 default case, cases 3-6,9-14,16,18-58
0x10040827c  lea     rsi, __ImageBase
0x100408283  cdqe
0x100408285  movzx   eax, ds:(byte_10040837C - 100400000h)[rsi+rax]
0x10040828d  mov     ecx, ds:(jpt_100408297 - 100400000h)[rsi+rax*4]
0x100408294  add     rcx, rsi
0x100408297  jmp     rcx; switch jump
0x100408299  mov     eax, [rbx+728h]; jumptable 0000000100408297 case 8
0x10040829f  mov     ecx, 7FFFFFFFh
0x1004082a4  test    eax, eax
0x1004082a6  cmovg   ecx, eax
0x1004082a9  mov     [rbx+134h], ecx
0x1004082af  lea     rcx, [rbx+28h]
0x1004082b3  mov     rax, [rbx+0D8h]
0x1004082ba  call    cs:__guard_dispatch_icall_fptr
0x1004082c0  mov     eax, [rbx+70h]
0x1004082c3  sub     eax, 3
0x1004082c6  cmp     eax, 38h ; '8'
0x1004082c9  ja      def_100408297; jumptable 0000000100408297 default case, cases 3-6,9-14,16,18-58
0x1004082cf  jmp     short loc_100408283
0x1004082d1  mov     rcx, rbx; jumptable 0000000100408297 case 15
0x1004082d4  mov     rsi, [rsp+38h+arg_0]
0x1004082d9  mov     rdi, [rsp+38h+arg_8]
0x1004082de  add     rsp, 30h
0x1004082e2  pop     rbx
0x1004082e3  jmp     ?ParseComment@YReader@@AEAAXXZ; YReader::ParseComment(void)
0x1004082e8  mov     rcx, rbx; jumptable 0000000100408297 case 17
0x1004082eb  mov     rsi, [rsp+38h+arg_0]
0x1004082f0  mov     rdi, [rsp+38h+arg_8]
0x1004082f5  add     rsp, 30h
0x1004082f9  pop     rbx
0x1004082fa  jmp     ?ParsePi@YReader@@AEAAXXZ; YReader::ParsePi(void)
0x1004082ff  mov     rsi, [rsp+38h+arg_0]; jumptable 0000000100408297 case 59
0x100408304  lea     rax, ?ParseDocumentEnd@YReader@@AEAAXXZ; YReader::ParseDocumentEnd(void)
0x10040830b  mov     rdi, [rsp+38h+arg_8]
0x100408310  xor     ecx, ecx
0x100408312  mov     qword ptr [rsp+38h+var_18], rax
0x100408317  mov     dword ptr [rsp+38h+var_18+8], ecx
0x10040831b  movups  xmm0, [rsp+38h+var_18]
0x100408320  mov     dword ptr [rbx+6F4h], 1
0x10040832a  mov     [rbx+6F0h], ecx
0x100408330  movups  xmmword ptr [rbx+5E0h], xmm0
0x100408337  add     rsp, 30h
0x10040833b  pop     rbx
0x10040833c  retn
0x10040833d  mov     ecx, 80004005h; int
0x100408342  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408347  int     3; Trap to Debugger
0x100408348  mov     ecx, 0C00CEE3Ah; jumptable 0000000100408297 default case, cases 3-6,9-14,16,18-58
0x10040834d  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408352  int     3; Trap to Debugger
0x100408353  mov     ecx, 0C00CEE2Dh; jumptable 0000000100408297 case 7
0x100408358  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040835d  int     3; Trap to Debugger
```
