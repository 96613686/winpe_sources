# CMemBufFormatter::write(char *,unsigned __int64)

- ea: `0x100430f30`
- end: `0x1004310af`
- name: `?write@CMemBufFormatter@@QEAA_KPEAD_K@Z`
- size: `383`
- prototype: `size_t __fastcall(CMemBufFormatter *this, char *, size_t)`
- caller_count: `47`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100438830`
- `0x100439120`
- `0x100439230`
- `0x10045e440`
- `0x10045f8e0`
- `0x1004602b0`
- `0x100467080`
- `0x1004671b0`
- `0x100467a60`
- `0x100468130`
- `0x100468460`
- `0x100468d60`
- `0x100478aa0`
- `0x100481640`
- `0x100481730`
- `0x100481a60`
- `0x1004826f0`
- `0x100482a50`
- `0x100482f60`
- `0x1004c9e80`
- `0x1004ca250`
- `0x1004ca940`
- `0x1004cb4d0`
- `0x1004cc520`
- `0x1004cc5d0`
- `0x1004cc7b0`
- `0x1004cce50`
- `0x1004cd0f0`
- `0x1004cd550`
- `0x1004ce760`
- `0x1004cee60`
- `0x1004d06c0`
- `0x1004d0d60`
- `0x1004d1650`
- `0x1004d32f0`
- `0x1004d3aa0`
- `0x1004d4250`
- `0x1004d6690`
- `0x1004d6870`
- `0x1004d6980`
- `0x1004d7340`
- `0x1004d8280`
- `0x1004da230`
- `0x1004da2b0`
- `0x1004db690`
- `0x1006fafc0`
- `0x1007272d0`

## callees

- `0x100401cc0`
- `0x100430f30`
- `0x1004310c0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100431015`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100431015`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100430fe6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100430fe6`

## string_xrefs

- `0x100430fd8`: `sql\common\dk\osf\src\formatter.cpp`
- `0x100431005`: `sql\common\dk\osf\src\formatter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
size_t __fastcall CMemBufFormatter::write(CMemBufFormatter *this, char *a2, size_t a3)
{
  size_t v6; // r15
  char **v7; // rsi
  __int64 v8; // rcx
  char *v9; // rbp
  _QWORD *v10; // rbx
  __int64 v11; // rdx
  _QWORD *v12; // rax
  size_t v13; // rbx
  char v15; // [rsp+90h] [rbp+18h] BYREF
  int v16; // [rsp+98h] [rbp+20h]

  v6 = a3;
  if ( a3 )
  {
    _mm_lfence();
    v7 = (char **)((char *)this + 16);
    do
    {
      if ( v7[1] == (char *)v7 || (v8 = *((_QWORD *)this + 10), v8 == *(_QWORD *)this) )
      {
        if ( *((_BYTE *)this + 40) )
        {
          v10 = (_QWORD *)(***(__int64 (__fastcall ****)(_QWORD, __int64, char *))(*((_QWORD *)this + 4) + 64LL))(
                            *(_QWORD *)(*((_QWORD *)this + 4) + 64LL),
                            1,
                            &v15);
          LOBYTE(v11) = 77;
          ex_oomCheck(v10, v11);
          v9 = (char *)(v10 + 3);
          *v10 = v10 + 3;
          v10[1] = 0;
          v10[2] = 0;
        }
        else
        {
          v9 = (char *)operator new[](
                         *(_QWORD *)this,
                         *((struct IMemObj **)this + 4),
                         "sql\\common\\dk\\osf\\src\\formatter.cpp",
                         189,
                         6u);
          v16 = 190;
          v12 = operator new(0x18u, *((struct IMemObj **)this + 4), "sql\\common\\dk\\osf\\src\\formatter.cpp", 190, 6u);
          v10 = v12;
          if ( v12 )
          {
            *v12 = v9;
            v12[1] = 0;
            v12[2] = 0;
          }
          else
          {
            v10 = 0;
          }
        }
        *((_QWORD *)this + 9) = v10;
        v7 = (char **)((char *)this + 16);
        v10[1] = *((_QWORD *)this + 2);
        *(_QWORD *)(*((_QWORD *)this + 2) + 8LL) = v10 + 1;
        *((_QWORD *)this + 2) = v10 + 1;
        v10[2] = (char *)this + 16;
        *((_QWORD *)this + 10) = 0;
        v8 = 0;
      }
      else
      {
        v9 = (char *)**((_QWORD **)this + 9);
      }
      v13 = v6;
      if ( v6 > *(_QWORD *)this - v8 )
        v13 = *(_QWORD *)this - v8;
      memmove(&v9[v8], &a2[a3 - v6], v13);
      *((_QWORD *)this + 10) += v13;
      v6 -= v13;
    }
    while ( v6 );
  }
  *((_QWORD *)this + 1) += a3;
  return a3;
}

```

## disassembly

```asm
0x100430f30  mov     [rsp+arg_0], rcx
0x100430f35  push    rbp
0x100430f36  push    rsi
0x100430f37  push    rdi
0x100430f38  push    r12
0x100430f3a  push    r13
0x100430f3c  push    r14
0x100430f3e  push    r15
0x100430f40  sub     rsp, 40h
0x100430f44  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x100430f4d  mov     [rsp+78h+arg_8], rbx
0x100430f55  mov     r14, r8
0x100430f58  mov     r12, rdx
0x100430f5b  mov     rdi, rcx
0x100430f5e  mov     r15, r8
0x100430f61  test    r8, r8
0x100430f64  jz      loc_100431090
0x100430f6a  lfence
0x100430f6d  lea     rsi, [rcx+10h]
0x100430f71  xor     r13d, r13d
0x100430f74  cmp     [rsi+8], rsi
0x100430f78  jz      short loc_100430F8F
0x100430f7a  mov     rcx, [rdi+50h]
0x100430f7e  cmp     rcx, [rdi]
0x100430f81  jz      short loc_100430F8F
0x100430f83  mov     rax, [rdi+48h]
0x100430f87  mov     rbp, [rax]
0x100430f8a  jmp     loc_10043105F
0x100430f8f  cmp     byte ptr [rdi+28h], 0
0x100430f93  jz      short loc_100430FCD
0x100430f95  mov     rax, [rdi+20h]
0x100430f99  mov     rcx, [rax+40h]
0x100430f9d  mov     rax, [rcx]
0x100430fa0  lea     r8, [rsp+78h+arg_10]
0x100430fa8  mov     edx, 1
0x100430fad  call    qword ptr [rax]
0x100430faf  mov     rbx, rax
0x100430fb2  mov     dl, 4Dh ; 'M'
0x100430fb4  mov     rcx, rax
0x100430fb7  call    ?ex_oomCheck@@YAXPEAXW4OOM_EXCEPTIONS@@@Z; ex_oomCheck(void *,OOM_EXCEPTIONS)
0x100430fbc  lea     rbp, [rbx+18h]
0x100430fc0  mov     [rbx], rbp
0x100430fc3  mov     [rbx+8], r13
0x100430fc7  mov     [rbx+10h], r13
0x100430fcb  jmp     short loc_100431038
0x100430fcd  mov     [rsp+78h+var_58], 6
0x100430fd2  mov     r9d, 0BDh
0x100430fd8  lea     r8, aSqlCommonDkOsf_0; "sql\\common\\dk\\osf\\src\\formatter.cp"...
0x100430fdf  mov     rdx, [rdi+20h]
0x100430fe3  mov     rcx, [rdi]
0x100430fe6  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100430fec  mov     rbp, rax
0x100430fef  mov     [rsp+78h+arg_18], 0BEh
0x100430ffa  mov     [rsp+78h+var_58], 6
0x100430fff  mov     r9d, 0BEh
0x100431005  lea     r8, aSqlCommonDkOsf_0; "sql\\common\\dk\\osf\\src\\formatter.cp"...
0x10043100c  mov     rdx, [rdi+20h]
0x100431010  mov     ecx, 18h
0x100431015  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10043101b  mov     rbx, rax
0x10043101e  mov     [rsp+78h+var_40], rax
0x100431023  test    rax, rax
0x100431026  jz      short loc_100431035
0x100431028  mov     [rax], rbp
0x10043102b  mov     [rax+8], r13
0x10043102f  mov     [rax+10h], r13
0x100431033  jmp     short loc_100431038
0x100431035  mov     rbx, r13
0x100431038  mov     [rdi+48h], rbx
0x10043103c  lea     rcx, [rbx+8]
0x100431040  lea     rsi, [rdi+10h]
0x100431044  mov     rax, [rsi]
0x100431047  mov     [rcx], rax
0x10043104a  mov     rax, [rsi]
0x10043104d  mov     [rax+8], rcx
0x100431051  mov     [rsi], rcx
0x100431054  mov     [rcx+8], rsi
0x100431058  mov     [rdi+50h], r13
0x10043105c  mov     rcx, r13
0x10043105f  mov     rax, [rdi]
0x100431062  sub     rax, rcx
0x100431065  mov     rbx, r15
0x100431068  cmp     r15, rax
0x10043106b  cmova   rbx, rax
0x10043106f  mov     rdx, r12
0x100431072  sub     rdx, r15
0x100431075  add     rdx, r14; Src
0x100431078  add     rcx, rbp; void *
0x10043107b  mov     r8, rbx; Size
0x10043107e  call    memmove
0x100431083  add     [rdi+50h], rbx
0x100431087  sub     r15, rbx
0x10043108a  jnz     loc_100430F74
0x100431090  add     [rdi+8], r14
0x100431094  mov     rax, r14
0x100431097  mov     rbx, [rsp+78h+arg_8]
0x10043109f  add     rsp, 40h
0x1004310a3  pop     r15
0x1004310a5  pop     r14
0x1004310a7  pop     r13
0x1004310a9  pop     r12
0x1004310ab  pop     rdi
0x1004310ac  pop     rsi
0x1004310ad  pop     rbp
0x1004310ae  retn
```
