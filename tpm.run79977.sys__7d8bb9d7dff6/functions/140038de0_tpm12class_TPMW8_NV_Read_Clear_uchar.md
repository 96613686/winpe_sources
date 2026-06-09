# tpm12class::TPMW8_NV_Read::Clear(uchar)

- ea: `0x140038de0`
- end: `0x140038e97`
- name: `?Clear@TPMW8_NV_Read@tpm12class@@MEAAJE@Z`
- size: `183`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_NV_Read *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140038c38`

## callees

- `0x14000cb50`
- `0x140034f84`
- `0x140035d90`
- `0x140038de0`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_NV_Read::Clear(tpm12class::TPMW8_NV_Read *this, char a2)
{
  int v2; // edi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  tpm12class::TPMW8_SESSION *v5; // rax
  struct tpm12class::TPMW8_AUTH_PROVIDER *v6; // rdx
  __int64 v7; // rax

  v2 = 0;
  if ( a2 || (v2 = tpm12class::TPMW8_COMMAND::Clear(this, 0), v2 >= 0) )
  {
    v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 21);
    *((_WORD *)this + 28) = -32766;
    if ( v4 )
    {
      (**v4)(v4, 1);
      *((_QWORD *)this + 21) = 0;
    }
    v5 = (tpm12class::TPMW8_SESSION *)operator new(0x318u);
    if ( v5 )
    {
      v7 = tpm12class::TPMW8_SESSION::TPMW8_SESSION(v5, v6);
      *((_QWORD *)this + 21) = v7;
      if ( v7 )
      {
        *((_DWORD *)this + 40) = 334;
        *((_DWORD *)this + 48) = 1073741831;
        *((_DWORD *)this + 68) = 1073741831;
        *((_DWORD *)this + 88) = 0;
        return (unsigned int)v2;
      }
    }
    else
    {
      *((_QWORD *)this + 21) = 0;
    }
    return (unsigned int)-2147024888;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140038de0  mov     [rsp+arg_0], rbx
0x140038de5  push    rdi
0x140038de6  sub     rsp, 20h
0x140038dea  xor     edi, edi
0x140038dec  mov     rbx, rcx
0x140038def  test    dl, dl
0x140038df1  jnz     short loc_140038E04
0x140038df3  xor     edx, edx; unsigned __int8
0x140038df5  call    ?Clear@TPMW8_COMMAND@tpm12class@@MEAAJE@Z; tpm12class::TPMW8_COMMAND::Clear(uchar)
0x140038dfa  mov     edi, eax
0x140038dfc  test    eax, eax
0x140038dfe  js      loc_140038E89
0x140038e04  mov     rcx, [rbx+0A8h]
0x140038e0b  mov     word ptr [rbx+38h], 8002h
0x140038e11  test    rcx, rcx
0x140038e14  jz      short loc_140038E31
0x140038e16  mov     rdx, [rcx]
0x140038e19  mov     rax, [rdx]
0x140038e1c  mov     edx, 1
0x140038e21  call    _guard_dispatch_icall
0x140038e26  mov     qword ptr [rbx+0A8h], 0
0x140038e31  mov     ecx, 318h; unsigned __int64
0x140038e36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140038e3b  test    rax, rax
0x140038e3e  jz      short loc_140038E79
0x140038e40  mov     rcx, rax; this
0x140038e43  call    ??0TPMW8_SESSION@tpm12class@@QEAA@PEAVTPMW8_AUTH_PROVIDER@1@@Z; tpm12class::TPMW8_SESSION::TPMW8_SESSION(tpm12class::TPMW8_AUTH_PROVIDER *)
0x140038e48  mov     [rbx+0A8h], rax
0x140038e4f  test    rax, rax
0x140038e52  jz      short loc_140038E84
0x140038e54  mov     eax, 40000007h
0x140038e59  mov     dword ptr [rbx+0A0h], 14Eh
0x140038e63  mov     [rbx+0C0h], eax
0x140038e69  mov     [rbx+110h], eax
0x140038e6f  xor     eax, eax
0x140038e71  mov     [rbx+160h], eax
0x140038e77  jmp     short loc_140038E89
0x140038e79  mov     qword ptr [rbx+0A8h], 0
0x140038e84  mov     edi, 80070008h
0x140038e89  mov     rbx, [rsp+28h+arg_0]
0x140038e8e  mov     eax, edi
0x140038e90  add     rsp, 20h
0x140038e94  pop     rdi
0x140038e95  retn
```
