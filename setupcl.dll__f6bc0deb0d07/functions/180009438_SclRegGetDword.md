# SclRegGetDword

- ea: `0x180009438`
- end: `0x180009526`
- name: `SclRegGetDword`
- size: `238`
- prototype: `__int64 __fastcall(HANDLE, const WCHAR *, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180002cc8`
- `0x1800065f8`

## callees

- `0x1800014e8`
- `0x180009438`
- `0x180009668`
- `0x18000a524`

## import_xrefs

- `ntdll!NtClose` at `0x180009514`
- `ntdll!NtClose` at `0x180009514`
- `ntdll!RtlFreeHeap` at `0x180009501`
- `ntdll!RtlFreeHeap` at `0x180009501`

## string_xrefs

- `0x1800094af`: `Value [%ws] is not registry DWORD value`

## pseudocode

```c
__int64 __fastcall SclRegGetDword(HANDLE a1, const WCHAR *a2, __int64 a3, _DWORD *a4)
{
  int Key; // edi
  ULONG v8; // [rsp+20h] [rbp-58h]
  HANDLE Handle; // [rsp+88h] [rbp+10h] BYREF

  Handle = 0;
  if ( a2 )
  {
    Key = SclCreateKey((__int64)a1, a2, 0xF003Fu, (__int64)&Handle);
    if ( Key < 0 )
      goto LABEL_9;
    a1 = Handle;
  }
  Key = SclRegGetValue(a1, v8);
  if ( Key >= 0 )
  {
    if ( MEMORY[4] == 4 && MEMORY[8] == 4 )
    {
      *a4 = MEMORY[0xC];
    }
    else
    {
      SclLogGenericMessage(
        0,
        3,
        (int)SclEvent_Generic_Error,
        1900,
        (__int64)"SclRegGetDword",
        "Value [%ws] is not registry DWORD value",
        a3);
      Key = -1073741788;
    }
  }
LABEL_9:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180009438  mov     rax, rsp
0x18000943b  push    rbx
0x18000943c  push    rsi
0x18000943d  push    rdi
0x18000943e  push    r14
0x180009440  sub     rsp, 58h
0x180009444  mov     qword ptr [rax+10h], 0
0x18000944c  mov     r14, r9
0x18000944f  mov     qword ptr [rax-38h], 0
0x180009457  mov     rsi, r8
0x18000945a  test    rdx, rdx
0x18000945d  jz      short loc_180009480
0x18000945f  lea     r9, [rax+10h]
0x180009463  mov     r8d, 0F003Fh
0x180009469  call    SclCreateKey
0x18000946e  mov     edi, eax
0x180009470  test    eax, eax
0x180009472  js      loc_180009507
0x180009478  mov     rcx, [rsp+78h+Handle]; KeyHandle
0x180009480  lea     r9, [rsp+78h+P]
0x180009485  xor     r8d, r8d
0x180009488  mov     rdx, rsi
0x18000948b  call    SclRegGetValue
0x180009490  mov     rbx, [rsp+78h+P]
0x180009495  mov     edi, eax
0x180009497  test    eax, eax
0x180009499  js      short loc_1800094EA
0x18000949b  cmp     dword ptr [rbx+4], 4
0x18000949f  jnz     short loc_1800094AF
0x1800094a1  cmp     dword ptr [rbx+8], 4
0x1800094a5  jnz     short loc_1800094AF
0x1800094a7  mov     ecx, [rbx+0Ch]
0x1800094aa  mov     [r14], ecx
0x1800094ad  jmp     short loc_1800094EA
0x1800094af  lea     rax, aValueWsIsNotRe_0; "Value [%ws] is not registry DWORD value"
0x1800094b6  mov     [rsp+78h+var_48], rsi
0x1800094bb  mov     [rsp+78h+var_50], rax
0x1800094c0  lea     r8, SclEvent_Generic_Error
0x1800094c7  lea     rax, aSclreggetdword; "SclRegGetDword"
0x1800094ce  mov     r9d, 76Ch
0x1800094d4  mov     edx, 3
0x1800094d9  mov     [rsp+78h+var_58], rax
0x1800094de  xor     ecx, ecx
0x1800094e0  call    SclLogGenericMessage
0x1800094e5  mov     edi, 0C0000024h
0x1800094ea  test    rbx, rbx
0x1800094ed  jz      short loc_180009507
0x1800094ef  mov     rcx, gs:60h
0x1800094f8  mov     r8, rbx; P
0x1800094fb  xor     edx, edx; Flags
0x1800094fd  mov     rcx, [rcx+30h]; HeapHandle
0x180009501  call    cs:__imp_RtlFreeHeap
0x180009507  mov     rcx, [rsp+78h+Handle]; Handle
0x18000950f  test    rcx, rcx
0x180009512  jz      short loc_18000951A
0x180009514  call    cs:__imp_NtClose
0x18000951a  mov     eax, edi
0x18000951c  add     rsp, 58h
0x180009520  pop     r14
0x180009522  pop     rdi
0x180009523  pop     rsi
0x180009524  pop     rbx
0x180009525  retn
```
