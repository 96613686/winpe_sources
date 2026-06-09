# IASCollection::get_Enumerator(IIASEnum * *)

- ea: `0x180030d20`
- end: `0x180030dd9`
- name: `?get_Enumerator@IASCollection@@UEAAJPEAPEAUIIASEnum@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(IASCollection *__hidden this, struct IIASEnum **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002fcd0`

## callees

- `0x18002cd00`
- `0x180030644`
- `0x180030d20`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x180030d73`: `CreateNewEnumerator() failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASCollection::get_Enumerator(IASCollection *this, struct IIASEnum **a2)
{
  int NewEnumerator; // ebx
  __int64 v6; // rcx

  if ( !a2 )
    return 2147500035LL;
  NewEnumerator = IASCollection::CreateNewEnumerator(this);
  if ( NewEnumerator >= 0 )
  {
    *a2 = (struct IIASEnum *)*((_QWORD *)this + 6);
    v6 = *((_QWORD *)this + 6);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("CreateNewEnumerator() failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_c2f236718121324f7e73e45b18920f9d_Traceguids,
        (unsigned int)"NPSSDO",
        NewEnumerator);
    }
    return (unsigned int)NewEnumerator;
  }
}

```

## disassembly

```asm
0x180030d20  mov     [rsp+arg_0], rbx
0x180030d25  mov     [rsp+arg_8], rsi
0x180030d2a  push    rdi
0x180030d2b  sub     rsp, 30h
0x180030d2f  mov     rsi, rdx
0x180030d32  mov     rdi, rcx
0x180030d35  test    rdx, rdx
0x180030d38  jnz     short loc_180030D44
0x180030d3a  mov     eax, 80004003h
0x180030d3f  jmp     loc_180030DC9
0x180030d44  call    ?CreateNewEnumerator@IASCollection@@QEAAJXZ; IASCollection::CreateNewEnumerator(void)
0x180030d49  mov     ebx, eax
0x180030d4b  test    eax, eax
0x180030d4d  jns     short loc_180030DAA
0x180030d4f  lea     rax, WPP_GLOBAL_Control
0x180030d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d5d  cmp     rcx, rax
0x180030d60  jz      short loc_180030DA6
0x180030d62  cmp     byte ptr [rcx+19h], 2
0x180030d66  jb      short loc_180030DA6
0x180030d68  test    dword ptr [rcx+1Ch], 400h
0x180030d6f  jz      short loc_180030DA6
0x180030d71  mov     edx, ebx
0x180030d73  lea     rcx, aCreatenewenume; "CreateNewEnumerator() failed with 0x%x"
0x180030d7a  call    WppDbgPrint
0x180030d7f  mov     edx, 17h
0x180030d84  mov     [rsp+38h+var_18], ebx
0x180030d88  lea     r9, aNpssdo; "NPSSDO"
0x180030d8f  lea     r8, WPP_c2f236718121324f7e73e45b18920f9d_Traceguids
0x180030d96  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d9d  mov     rcx, [rcx+10h]
0x180030da1  call    WPP_SF_sd
0x180030da6  mov     eax, ebx
0x180030da8  jmp     short loc_180030DC9
0x180030daa  mov     rax, [rdi+30h]
0x180030dae  mov     [rsi], rax
0x180030db1  mov     rcx, [rdi+30h]
0x180030db5  test    rcx, rcx
0x180030db8  jz      short loc_180030DC7
0x180030dba  mov     rax, [rcx]
0x180030dbd  mov     rax, [rax+8]
0x180030dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030dc6  nop
0x180030dc7  xor     eax, eax
0x180030dc9  mov     rbx, [rsp+38h+arg_0]
0x180030dce  mov     rsi, [rsp+38h+arg_8]
0x180030dd3  add     rsp, 30h
0x180030dd7  pop     rdi
0x180030dd8  retn
```
