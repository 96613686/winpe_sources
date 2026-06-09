# SclRegGetString

- ea: `0x18000952c`
- end: `0x180009661`
- name: `SclRegGetString`
- size: `309`
- prototype: `__int64 __fastcall(HANDLE, const WCHAR *, __int64, _WORD *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180002010`
- `0x1800073c4`
- `0x18000bc68`

## callees

- `0x180001464`
- `0x1800014e8`
- `0x18000952c`
- `0x180009668`
- `0x18000a524`

## import_xrefs

- `ntdll!NtClose` at `0x18000964f`
- `ntdll!NtClose` at `0x18000964f`
- `ntdll!RtlFreeHeap` at `0x18000963c`
- `ntdll!RtlFreeHeap` at `0x18000963c`

## string_xrefs

- `0x1800095ea`: `Value [%ws] is not registry string value`

## pseudocode

```c
__int64 __fastcall SclRegGetString(HANDLE a1, const WCHAR *a2, __int64 a3, _WORD *a4, unsigned int a5)
{
  int Key; // ebx
  ULONG v9; // [rsp+20h] [rbp-58h]
  HANDLE Handle; // [rsp+88h] [rbp+10h] BYREF

  Handle = 0;
  if ( a2 )
  {
    Key = SclCreateKey((__int64)a1, a2, 0xF003Fu, (__int64)&Handle);
    if ( Key < 0 )
      goto LABEL_12;
    a1 = Handle;
  }
  Key = SclRegGetValue(a1, v9);
  if ( Key >= 0 )
  {
    if ( ((MEMORY[4] - 1) & 0xFFFFFFFA) != 0 || MEMORY[4] == 5 )
    {
      SclLogGenericMessage(
        0,
        3,
        (int)SclEvent_Generic_Error,
        1810,
        (__int64)"SclRegGetString",
        "Value [%ws] is not registry string value",
        a3);
      Key = -1073741788;
    }
    else if ( a5 > MEMORY[8] >> 1 )
    {
      Key = RtlStringCchCopyNW(a4, a5 - 1, (_WORD *)0xC, (unsigned __int64)MEMORY[8] >> 1);
      if ( Key >= 0 )
        a4[(unsigned __int64)MEMORY[8] >> 1] = 0;
    }
    else
    {
      Key = -2147483643;
    }
  }
LABEL_12:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x18000952c  mov     rax, rsp
0x18000952f  push    rbx
0x180009530  push    rsi
0x180009531  push    rdi
0x180009532  push    r14
0x180009534  sub     rsp, 58h
0x180009538  mov     qword ptr [rax+10h], 0
0x180009540  mov     r14, r9
0x180009543  mov     qword ptr [rax-38h], 0
0x18000954b  mov     rsi, r8
0x18000954e  test    rdx, rdx
0x180009551  jz      short loc_180009574
0x180009553  lea     r9, [rax+10h]
0x180009557  mov     r8d, 0F003Fh
0x18000955d  call    SclCreateKey
0x180009562  mov     ebx, eax
0x180009564  test    eax, eax
0x180009566  js      loc_180009642
0x18000956c  mov     rcx, [rsp+78h+Handle]; KeyHandle
0x180009574  lea     r9, [rsp+78h+P]
0x180009579  mov     r8d, 10h
0x18000957f  mov     rdx, rsi
0x180009582  call    SclRegGetValue
0x180009587  mov     rdi, [rsp+78h+P]
0x18000958c  mov     ebx, eax
0x18000958e  test    eax, eax
0x180009590  js      loc_180009625
0x180009596  mov     ecx, [rdi+4]
0x180009599  lea     eax, [rcx-1]
0x18000959c  test    eax, 0FFFFFFFAh
0x1800095a1  jnz     short loc_1800095EA
0x1800095a3  cmp     ecx, 5
0x1800095a6  jz      short loc_1800095EA
0x1800095a8  mov     eax, [rdi+8]
0x1800095ab  mov     ecx, [rsp+78h+arg_20]
0x1800095b2  shr     eax, 1
0x1800095b4  cmp     ecx, eax
0x1800095b6  ja      short loc_1800095BF
0x1800095b8  mov     ebx, 80000005h
0x1800095bd  jmp     short loc_180009625
0x1800095bf  mov     r9d, [rdi+8]
0x1800095c3  lea     edx, [rcx-1]
0x1800095c6  shr     r9, 1
0x1800095c9  lea     r8, [rdi+0Ch]
0x1800095cd  mov     rcx, r14
0x1800095d0  call    RtlStringCchCopyNW
0x1800095d5  mov     ebx, eax
0x1800095d7  test    eax, eax
0x1800095d9  js      short loc_180009625
0x1800095db  mov     ecx, [rdi+8]
0x1800095de  shr     rcx, 1
0x1800095e1  xor     eax, eax
0x1800095e3  mov     [r14+rcx*2], ax
0x1800095e8  jmp     short loc_180009625
0x1800095ea  lea     rax, aValueWsIsNotRe; "Value [%ws] is not registry string valu"...
0x1800095f1  mov     [rsp+78h+var_48], rsi
0x1800095f6  mov     [rsp+78h+var_50], rax
0x1800095fb  lea     r8, SclEvent_Generic_Error
0x180009602  lea     rax, aSclreggetstrin; "SclRegGetString"
0x180009609  mov     r9d, 712h
0x18000960f  mov     edx, 3
0x180009614  mov     [rsp+78h+var_58], rax
0x180009619  xor     ecx, ecx
0x18000961b  call    SclLogGenericMessage
0x180009620  mov     ebx, 0C0000024h
0x180009625  test    rdi, rdi
0x180009628  jz      short loc_180009642
0x18000962a  mov     rcx, gs:60h
0x180009633  mov     r8, rdi; P
0x180009636  xor     edx, edx; Flags
0x180009638  mov     rcx, [rcx+30h]; HeapHandle
0x18000963c  call    cs:__imp_RtlFreeHeap
0x180009642  mov     rcx, [rsp+78h+Handle]; Handle
0x18000964a  test    rcx, rcx
0x18000964d  jz      short loc_180009655
0x18000964f  call    cs:__imp_NtClose
0x180009655  mov     eax, ebx
0x180009657  add     rsp, 58h
0x18000965b  pop     r14
0x18000965d  pop     rdi
0x18000965e  pop     rsi
0x18000965f  pop     rbx
0x180009660  retn
```
