# SXWriter::writeBuffer(void)

- ea: `0x1004086f0`
- end: `0x1004087cf`
- name: `?writeBuffer@SXWriter@@IEAAXXZ`
- size: `223`
- prototype: `void __fastcall(SXWriter *__hidden this)`
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x1004087e0`
- `0x100408840`
- `0x100408d00`
- `0x100408d60`
- `0x1004091f0`
- `0x1004092b0`
- `0x100409320`
- `0x1004093d0`
- `0x1004095b0`
- `0x100409660`
- `0x100409740`
- `0x1004097a0`
- `0x100409840`
- `0x100409da0`
- `0x10040a3c0`
- `0x10040a470`
- `0x10040ace0`
- `0x10040adb0`
- `0x10040ae00`
- `0x10040ae60`

## callees

- `0x100401350`
- `0x1004086f0`
- `0x100424580`

## pseudocode

```c
void __fastcall SXWriter::writeBuffer(SXWriter *this)
{
  __int64 v2; // rcx
  SXWriter *v3; // rbx
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rax
  char *v7; // rsi
  unsigned int i; // ebx
  int v9; // eax
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 15);
  if ( !v2 )
  {
    MXRRaiseException(-2147467259);
    __debugbreak();
  }
  v3 = (SXWriter *)*((_QWORD *)this + 38);
  if ( v3 != (SXWriter *)((char *)this + 353) )
  {
    v4 = (_DWORD)v3 - (_DWORD)this - 353;
    v5 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, unsigned int *))(*(_QWORD *)v2 + 32LL))(
           v2,
           (char *)this + 353,
           v4,
           &v10);
    if ( v5 < 0 )
    {
      _mm_lfence();
      MXRRaiseException(v5);
      __debugbreak();
    }
    v6 = v10;
    if ( v10 != v4 )
    {
      v7 = (char *)this + 353;
      for ( i = v4 - v10; i; i -= v10 )
      {
        v7 += v6;
        v9 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, unsigned int *))(**((_QWORD **)this + 15) + 32LL))(
               *((_QWORD *)this + 15),
               v7,
               i,
               &v10);
        if ( v9 < 0 )
        {
          _mm_lfence();
          MXRRaiseException(v9);
          JUMPOUT(0x1004087CELL);
        }
        v6 = v10;
      }
    }
    *((_QWORD *)this + 38) = (char *)this + 353;
    *((_BYTE *)this + 251) = 1;
  }
}

```

## disassembly

```asm
0x1004086f0  push    rdi
0x1004086f2  sub     rsp, 30h
0x1004086f6  mov     rdi, rcx
0x1004086f9  mov     rcx, [rcx+78h]
0x1004086fd  test    rcx, rcx
0x100408700  jz      loc_1004087AE
0x100408706  mov     [rsp+38h+arg_8], rbx
0x10040870b  mov     rbx, [rdi+130h]
0x100408712  mov     [rsp+38h+arg_10], rbp
0x100408717  lea     rbp, [rdi+161h]
0x10040871e  cmp     rbx, rbp
0x100408721  jz      short loc_10040879E
0x100408723  mov     rax, [rcx]
0x100408726  lea     r9, [rsp+38h+arg_0]
0x10040872b  sub     ebx, edi
0x10040872d  mov     rdx, rbp
0x100408730  sub     ebx, 161h
0x100408736  mov     r8d, ebx
0x100408739  mov     rax, [rax+20h]
0x10040873d  call    cs:__guard_dispatch_icall_fptr
0x100408743  test    eax, eax
0x100408745  js      short loc_1004087B9
0x100408747  mov     eax, [rsp+38h+arg_0]
0x10040874b  mov     [rsp+38h+arg_18], rsi
0x100408750  cmp     eax, ebx
0x100408752  jz      short loc_10040878B
0x100408754  mov     rsi, rbp
0x100408757  sub     ebx, eax
0x100408759  jz      short loc_10040878B
0x10040875b  nop     dword ptr [rax+rax+00h]
0x100408760  mov     rcx, [rdi+78h]
0x100408764  lea     r9, [rsp+38h+arg_0]
0x100408769  add     rsi, rax
0x10040876c  mov     r8d, ebx
0x10040876f  mov     rdx, rsi
0x100408772  mov     rax, [rcx]
0x100408775  mov     rax, [rax+20h]
0x100408779  call    cs:__guard_dispatch_icall_fptr
0x10040877f  test    eax, eax
0x100408781  js      short loc_1004087C4
0x100408783  mov     eax, [rsp+38h+arg_0]
0x100408787  sub     ebx, eax
0x100408789  jnz     short loc_100408760
0x10040878b  mov     rsi, [rsp+38h+arg_18]
0x100408790  mov     [rdi+130h], rbp
0x100408797  mov     byte ptr [rdi+0FBh], 1
0x10040879e  mov     rbx, [rsp+38h+arg_8]
0x1004087a3  mov     rbp, [rsp+38h+arg_10]
0x1004087a8  add     rsp, 30h
0x1004087ac  pop     rdi
0x1004087ad  retn
0x1004087ae  mov     ecx, 80004005h; int
0x1004087b3  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004087b8  int     3; Trap to Debugger
0x1004087b9  lfence
0x1004087bc  mov     ecx, eax; int
0x1004087be  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004087c3  int     3; Trap to Debugger
0x1004087c4  lfence
0x1004087c7  mov     ecx, eax; int
0x1004087c9  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
