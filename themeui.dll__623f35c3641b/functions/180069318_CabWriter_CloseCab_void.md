# CabWriter::CloseCab(void)

- ea: `0x180069318`
- end: `0x1800693bd`
- name: `?CloseCab@CabWriter@@QEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(CabWriter *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180066e28`
- `0x18006917c`

## callees

- `0x180069318`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180069376`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180069376`
- `Cabinet!__imp_FCIFlushCabinet` at `0x18006934d`
- `Cabinet!__imp_FCIFlushCabinet` at `0x18006934d`
- `Cabinet!__imp_FCIDestroy` at `0x180069383`
- `Cabinet!__imp_FCIDestroy` at `0x180069383`

## pseudocode

```c
__int64 __fastcall CabWriter::CloseCab(CabWriter *this)
{
  void *v2; // rcx
  unsigned int v3; // edi
  BOOL v4; // ecx
  unsigned int v5; // esi
  __int64 result; // rax

  v2 = (void *)*((_QWORD *)this + 131);
  if ( v2 )
  {
    v4 = FCIFlushCabinet(v2, 0, (PFNFCIGETNEXTCABINET)CabWriter::FciGetNextCabinet, CabWriter::FciStatus);
    v5 = !v4 ? 0x80004005 : 0;
    if ( !*((_DWORD *)this + 465) || !v4 )
      DeleteFileW((LPCWSTR)this + 262);
    if ( !FCIDestroy(*((HFCI *)this + 131)) )
      v5 = -2147467259;
    v3 = v5;
  }
  else
  {
    v3 = -2147467259;
  }
  *((_WORD *)this + 262) = 0;
  result = v3;
  *((_QWORD *)this + 131) = 0;
  *((_BYTE *)this + 4) = 0;
  *((_BYTE *)this + 264) = 0;
  return result;
}

```

## disassembly

```asm
0x180069318  mov     [rsp+arg_0], rbx
0x18006931d  mov     [rsp+arg_8], rsi
0x180069322  push    rdi
0x180069323  sub     rsp, 20h
0x180069327  mov     rbx, rcx
0x18006932a  mov     rcx, [rcx+418h]; hfci
0x180069331  test    rcx, rcx
0x180069334  jnz     short loc_18006933D
0x180069336  mov     edi, 80004005h
0x18006933b  jmp     short loc_180069390
0x18006933d  lea     r9, ?FciStatus@CabWriter@@CAJIKKPEAX@Z; pfnfcis
0x180069344  xor     edx, edx; fGetNextCab
0x180069346  lea     r8, ?FciGetNextCabinet@CabWriter@@CAHPEAUCCAB@@KPEAX@Z; pfnfcignc
0x18006934d  call    cs:__imp_FCIFlushCabinet
0x180069353  mov     ecx, eax
0x180069355  mov     edi, 80004005h
0x18006935a  neg     eax
0x18006935c  sbb     esi, esi
0x18006935e  not     esi
0x180069360  and     esi, edi
0x180069362  cmp     dword ptr [rbx+744h], 0
0x180069369  jz      short loc_18006936F
0x18006936b  test    ecx, ecx
0x18006936d  jnz     short loc_18006937C
0x18006936f  lea     rcx, [rbx+20Ch]; lpFileName
0x180069376  call    cs:__imp_DeleteFileW
0x18006937c  mov     rcx, [rbx+418h]; hfci
0x180069383  call    cs:__imp_FCIDestroy
0x180069389  test    eax, eax
0x18006938b  cmovz   esi, edi
0x18006938e  mov     edi, esi
0x180069390  mov     rsi, [rsp+28h+arg_8]
0x180069395  xor     ecx, ecx
0x180069397  mov     [rbx+20Ch], cx
0x18006939e  mov     eax, edi
0x1800693a0  mov     [rbx+418h], rcx
0x1800693a7  mov     byte ptr [rbx+4], 0
0x1800693ab  mov     byte ptr [rbx+108h], 0
0x1800693b2  mov     rbx, [rsp+28h+arg_0]
0x1800693b7  add     rsp, 20h
0x1800693bb  pop     rdi
0x1800693bc  retn
```
