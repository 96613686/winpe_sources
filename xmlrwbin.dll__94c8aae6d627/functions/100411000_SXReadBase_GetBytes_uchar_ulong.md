# SXReadBase::GetBytes(uchar *,ulong)

- ea: `0x100411000`
- end: `0x10041114f`
- name: `?GetBytes@SXReadBase@@IEAAXPEAEK@Z`
- size: `335`
- prototype: `void __fastcall(SXReadBase *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x100405a70`
- `0x10040ed00`
- `0x10040edb0`
- `0x10040f590`
- `0x10040f9a0`
- `0x10040fbf0`
- `0x10040ff60`
- `0x100412db0`

## callees

- `0x100401350`
- `0x100411000`
- `0x100411160`
- `0x100415d60`
- `0x100424580`

## pseudocode

```c
void __fastcall SXReadBase::GetBytes(SXReadBase *this, unsigned __int8 *a2, unsigned int a3)
{
  unsigned int v3; // edi
  unsigned int v6; // eax
  __int64 v7; // rbp
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ecx
  __int64 v12; // rcx
  unsigned int v13; // [rsp+60h] [rbp+18h] BYREF

  if ( a3 )
  {
    v3 = a3;
    do
    {
      v6 = v3;
      if ( *((_DWORD *)this + 358) - *((_DWORD *)this + 356) < v3 )
        v6 = *((_DWORD *)this + 358) - *((_DWORD *)this + 356);
      v7 = v6;
      memmove(a2, *((const void **)this + 178), v6);
      *((_QWORD *)this + 178) += v7;
      v3 -= v7;
      if ( !v3 )
        break;
      a2 += v7;
      if ( v3 <= *((_DWORD *)this + 353) )
      {
        if ( !SXReadBase::Pull(this) )
          goto LABEL_22;
      }
      else
      {
        v8 = *((_QWORD *)this + 177);
        *((_QWORD *)this + 179) = v8;
        for ( *((_QWORD *)this + 178) = v8; !*((_BYTE *)this + 1448); a2 += v11 )
        {
          if ( !v3 )
            return;
          v9 = *((_QWORD *)this + 180);
          if ( v9 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, unsigned int *))(*(_QWORD *)v9 + 24LL))(
                    v9,
                    a2,
                    v3,
                    &v13);
            if ( v10 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v10);
              __debugbreak();
            }
            v11 = v13;
            if ( v13 )
              goto LABEL_15;
            v12 = *((_QWORD *)this + 180);
            *((_BYTE *)this + 1448) = 1;
            if ( v12 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              *((_QWORD *)this + 180) = 0;
            }
          }
          v11 = 0;
LABEL_15:
          v3 -= v11;
        }
        if ( v3 )
        {
LABEL_22:
          MXRRaiseException(-1072896679);
          JUMPOUT(0x10041114ELL);
        }
      }
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x100411000  test    r8d, r8d
0x100411003  jz      locret_100411138
0x100411009  push    rbx
0x10041100a  push    rsi
0x10041100b  push    rdi
0x10041100c  sub     rsp, 30h
0x100411010  mov     [rsp+48h+arg_0], rbp
0x100411015  mov     edi, r8d
0x100411018  mov     [rsp+48h+arg_8], r14
0x10041101d  mov     rsi, rdx
0x100411020  xor     r14d, r14d
0x100411023  mov     rbx, rcx
0x100411026  nop     word ptr [rax+rax+00000000h]
0x100411030  mov     ecx, [rbx+598h]
0x100411036  mov     eax, edi
0x100411038  sub     ecx, [rbx+590h]
0x10041103e  mov     rdx, [rbx+590h]; Src
0x100411045  cmp     ecx, edi
0x100411047  cmovb   eax, ecx
0x10041104a  mov     rcx, rsi; void *
0x10041104d  mov     r8d, eax; Size
0x100411050  mov     ebp, eax
0x100411052  call    memmove
0x100411057  add     [rbx+590h], rbp
0x10041105e  sub     edi, ebp
0x100411060  jz      loc_100411127
0x100411066  add     rsi, rbp
0x100411069  cmp     edi, [rbx+584h]
0x10041106f  jbe     loc_100411113
0x100411075  mov     rax, [rbx+588h]
0x10041107c  mov     [rbx+598h], rax
0x100411083  mov     [rbx+590h], rax
0x10041108a  cmp     [rbx+5A8h], r14b
0x100411091  jnz     short loc_10041110D
0x100411093  xor     al, al
0x100411095  test    edi, edi
0x100411097  jz      loc_100411127
0x10041109d  test    al, al
0x10041109f  jnz     short loc_1004110F8
0x1004110a1  mov     rcx, [rbx+5A0h]
0x1004110a8  test    rcx, rcx
0x1004110ab  jz      short loc_1004110F8
0x1004110ad  mov     rax, [rcx]
0x1004110b0  lea     r9, [rsp+48h+arg_10]
0x1004110b5  mov     r8d, edi
0x1004110b8  mov     rdx, rsi
0x1004110bb  mov     rax, [rax+18h]
0x1004110bf  call    cs:__guard_dispatch_icall_fptr
0x1004110c5  test    eax, eax
0x1004110c7  js      short loc_100411139
0x1004110c9  mov     ecx, [rsp+48h+arg_10]
0x1004110cd  test    ecx, ecx
0x1004110cf  jnz     short loc_1004110FB
0x1004110d1  mov     rcx, [rbx+5A0h]
0x1004110d8  mov     byte ptr [rbx+5A8h], 1
0x1004110df  test    rcx, rcx
0x1004110e2  jz      short loc_1004110F8
0x1004110e4  mov     rax, [rcx]
0x1004110e7  mov     rax, [rax+10h]
0x1004110eb  call    cs:__guard_dispatch_icall_fptr
0x1004110f1  mov     [rbx+5A0h], r14
0x1004110f8  mov     ecx, r14d
0x1004110fb  mov     eax, ecx
0x1004110fd  sub     edi, ecx
0x1004110ff  add     rsi, rax
0x100411102  movzx   eax, byte ptr [rbx+5A8h]
0x100411109  test    al, al
0x10041110b  jz      short loc_100411095
0x10041110d  test    edi, edi
0x10041110f  jnz     short loc_100411144
0x100411111  jmp     short loc_10041111F
0x100411113  mov     rcx, rbx; this
0x100411116  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10041111b  test    al, al
0x10041111d  jz      short loc_100411144
0x10041111f  test    edi, edi
0x100411121  jnz     loc_100411030
0x100411127  mov     rbp, [rsp+48h+arg_0]
0x10041112c  mov     r14, [rsp+48h+arg_8]
0x100411131  add     rsp, 30h
0x100411135  pop     rdi
0x100411136  pop     rsi
0x100411137  pop     rbx
0x100411138  retn
0x100411139  lfence
0x10041113c  mov     ecx, eax; int
0x10041113e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100411143  int     3; Trap to Debugger
0x100411144  mov     ecx, 0C00CE559h; int
0x100411149  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
