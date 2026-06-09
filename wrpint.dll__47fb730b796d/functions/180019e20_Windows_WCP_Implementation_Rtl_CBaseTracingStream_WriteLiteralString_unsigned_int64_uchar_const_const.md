# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(unsigned __int64,uchar const * const)

- ea: `0x180019e20`
- end: `0x180019ece`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_KQEBE@Z`
- size: `174`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64, const unsigned __int8 *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019e20`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        __int64 a2,
        const unsigned __int8 *a3,
        __int64 a4)
{
  const unsigned __int8 *v4; // rbx
  const unsigned __int8 *v6; // rbp
  unsigned __int64 v7; // rsi
  unsigned __int64 i; // rcx
  __int64 v9; // rdx
  char v10; // al

  if ( a2 )
  {
    v4 = a3;
    if ( a3 )
    {
      v6 = &a3[a2];
      if ( *((_BYTE *)this + 2132) || (v7 = 2047, NtCurrentPeb()->BeingDebugged) )
        v7 = 510;
      for ( i = *((_QWORD *)this + 3); ; ++i )
      {
        if ( i >= v7 )
        {
          *((_QWORD *)this + 3) = 0;
          v9 = 2047;
          LOBYTE(a4) = 1;
          if ( v7 < 0x7FF )
            v9 = v7;
          *((_BYTE *)this + v9 + 32) = 0;
          (*(void (__fastcall **)(_QWORD, __int64, char *, __int64))(**((_QWORD **)this + 1) + 8LL))(
            *((_QWORD *)this + 1),
            v9,
            (char *)this + 32,
            a4);
          i = 0;
          *((_BYTE *)this + 2134) = 1;
        }
        if ( v4 >= v6 )
          break;
        v10 = *v4++;
        *((_BYTE *)this + i + 32) = v10;
      }
      *((_QWORD *)this + 3) = i;
    }
  }
}

```

## disassembly

```asm
0x180019e20  test    rdx, rdx
0x180019e23  jz      locret_180019ECD
0x180019e29  push    rbx
0x180019e2a  push    rbp
0x180019e2b  push    rsi
0x180019e2c  push    rdi
0x180019e2d  push    r15
0x180019e2f  sub     rsp, 30h
0x180019e33  mov     rbx, r8
0x180019e36  mov     rdi, rcx
0x180019e39  test    rbx, rbx
0x180019e3c  jz      loc_180019EC3
0x180019e42  cmp     byte ptr [rcx+854h], 0
0x180019e49  lea     rbp, [rdx+r8]
0x180019e4d  mov     r15d, 7FFh
0x180019e53  jnz     short loc_180019E67
0x180019e55  mov     rax, gs:60h
0x180019e5e  mov     esi, r15d
0x180019e61  cmp     byte ptr [rax+2], 0
0x180019e65  jz      short loc_180019E6C
0x180019e67  mov     esi, 1FEh
0x180019e6c  mov     rcx, [rcx+18h]
0x180019e70  cmp     rcx, rsi
0x180019e73  jb      short loc_180019EAC
0x180019e75  mov     qword ptr [rdi+18h], 0
0x180019e7d  lea     r8, [rdi+20h]
0x180019e81  cmp     rsi, r15
0x180019e84  mov     rdx, r15
0x180019e87  mov     r9b, 1
0x180019e8a  cmovb   rdx, rsi
0x180019e8e  mov     byte ptr [rdx+rdi+20h], 0
0x180019e93  mov     rcx, [rdi+8]
0x180019e97  mov     rax, [rcx]
0x180019e9a  mov     rax, [rax+8]
0x180019e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ea3  xor     ecx, ecx
0x180019ea5  mov     byte ptr [rdi+856h], 1
0x180019eac  cmp     rbx, rbp
0x180019eaf  jnb     short loc_180019EBF
0x180019eb1  mov     al, [rbx]
0x180019eb3  inc     rbx
0x180019eb6  mov     [rcx+rdi+20h], al
0x180019eba  inc     rcx
0x180019ebd  jmp     short loc_180019E70
0x180019ebf  mov     [rdi+18h], rcx
0x180019ec3  add     rsp, 30h
0x180019ec7  pop     r15
0x180019ec9  pop     rdi
0x180019eca  pop     rsi
0x180019ecb  pop     rbp
0x180019ecc  pop     rbx
0x180019ecd  retn
```
