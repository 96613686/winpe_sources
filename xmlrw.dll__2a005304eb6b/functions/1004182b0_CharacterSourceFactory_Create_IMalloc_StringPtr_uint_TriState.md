# CharacterSourceFactory::Create(IMalloc *,StringPtr *,uint,TriState)

- ea: `0x1004182b0`
- end: `0x10041831c`
- name: `?Create@CharacterSourceFactory@@SAPEAVCharacterSource@@PEAUIMalloc@@PEAUStringPtr@@IW4TriState@@@Z`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10040f160`

## callees

- `0x100401780`
- `0x1004182b0`
- `0x100418490`
- `0x1004186a0`
- `0x100439df0`

## pseudocode

```c
MlangCharacterSource *__fastcall CharacterSourceFactory::Create(
        struct IMalloc *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 (__fastcall *Constructor)(struct IMalloc *, _QWORD); // rax
  MlangCharacterSource *result; // rax
  _DWORD v9[6]; // [rsp+20h] [rbp-18h] BYREF

  Constructor = (__int64 (__fastcall *)(struct IMalloc *, _QWORD))CharacterSourceFactory::FindConstructor(
                                                                    a2,
                                                                    a3,
                                                                    a4,
                                                                    v9);
  if ( Constructor )
    result = (MlangCharacterSource *)Constructor(a1, v9[0]);
  else
    result = CharacterSourceFactory::CreateMLangCharacterSource(a1, a2, a3);
  if ( !result )
  {
    MXRRaiseException(-1072894462);
    JUMPOUT(0x10041831BLL);
  }
  return result;
}

```

## disassembly

```asm
0x1004182b0  mov     [rsp+arg_0], rbx
0x1004182b5  mov     [rsp+arg_8], rsi
0x1004182ba  push    rdi
0x1004182bb  sub     rsp, 30h
0x1004182bf  mov     eax, r9d
0x1004182c2  mov     edi, r8d
0x1004182c5  mov     rsi, rdx
0x1004182c8  lea     r9, [rsp+38h+var_18]
0x1004182cd  mov     rbx, rcx
0x1004182d0  mov     r8d, eax
0x1004182d3  mov     edx, edi
0x1004182d5  mov     rcx, rsi
0x1004182d8  call    ?FindConstructor@CharacterSourceFactory@@CAP6APEAVCharacterSource@@PEAUIMalloc@@I@ZPEAUStringPtr@@IW4TriState@@PEAI@Z; CharacterSourceFactory::FindConstructor(StringPtr *,uint,TriState,uint *)
0x1004182dd  mov     rcx, rbx
0x1004182e0  test    rax, rax
0x1004182e3  jz      short loc_1004182F1
0x1004182e5  mov     edx, [rsp+38h+var_18]
0x1004182e9  call    cs:__guard_dispatch_icall_fptr
0x1004182ef  jmp     short loc_1004182FC
0x1004182f1  mov     r8d, edi
0x1004182f4  mov     rdx, rsi
0x1004182f7  call    ?CreateMLangCharacterSource@CharacterSourceFactory@@CAPEAVCharacterSource@@PEAUIMalloc@@PEAUStringPtr@@IW4TriState@@@Z; CharacterSourceFactory::CreateMLangCharacterSource(IMalloc *,StringPtr *,uint,TriState)
0x1004182fc  test    rax, rax
0x1004182ff  jz      short loc_100418311
0x100418301  mov     rbx, [rsp+38h+arg_0]
0x100418306  mov     rsi, [rsp+38h+arg_8]
0x10041830b  add     rsp, 30h
0x10041830f  pop     rdi
0x100418310  retn
0x100418311  mov     ecx, 0C00CEE02h; int
0x100418316  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
