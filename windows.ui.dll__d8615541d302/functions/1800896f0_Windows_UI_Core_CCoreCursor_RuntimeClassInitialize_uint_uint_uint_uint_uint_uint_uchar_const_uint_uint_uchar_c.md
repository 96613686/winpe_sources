# Windows::UI::Core::CCoreCursor::RuntimeClassInitialize(uint,uint,uint,uint,uint,uint,uchar const *,uint,uint,uchar const *,uint,uint)

- ea: `0x1800896f0`
- end: `0x1800897e9`
- name: `?RuntimeClassInitialize@CCoreCursor@Core@UI@Windows@@UEAAJIIIIIIPEBEII0II@Z`
- size: `249`
- prototype: `__int64 __fastcall(Windows::UI::Core::CCoreCursor *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, const unsigned __int8 *, unsigned int, unsigned int, const unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180014754`
- `0x180061ac8`
- `0x1800896f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800897b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800897b7`
- `ext-ms-win-rtcore-minuser-input-l1-1-4!CreateCursorFromBitmap` at `0x1800897a8`
- `ext-ms-win-rtcore-minuser-input-l1-1-4!CreateCursorFromBitmap` at `0x1800897a8`

## string_xrefs

- `0x18008971f`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\cursorfactory.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CCoreCursor::RuntimeClassInitialize(
        Windows::UI::Core::CCoreCursor *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 CursorFromBitmap; // rax
  signed int LastError; // eax
  int v15; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !(unsigned __int8)IsCreateCursorFromBitmapPresent() )
  {
    v10 = -2147467263;
    v11 = 232;
    goto LABEL_3;
  }
  v15 = a6;
  *((_QWORD *)this + 9) = 2;
  CursorFromBitmap = CreateCursorFromBitmap(a2, a3, a4, a5);
  *((_QWORD *)this + 10) = CursorFromBitmap;
  if ( !CursorFromBitmap )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (v10 & 0x80000000) == 0 )
      return v10;
    v11 = 251;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\cursorfactory.cpp",
      (const char *)v10,
      v15);
    return v10;
  }
  return 0;
}

```

## disassembly

```asm
0x1800896f0  push    rbx
0x1800896f2  push    rbp
0x1800896f3  push    rsi
0x1800896f4  push    rdi
0x1800896f5  sub     rsp, 68h
0x1800896f9  mov     edi, r9d
0x1800896fc  mov     esi, r8d
0x1800896ff  mov     ebp, edx
0x180089701  mov     rbx, rcx
0x180089704  call    IsCreateCursorFromBitmapPresent
0x180089709  test    al, al
0x18008970b  jnz     short loc_180089735
0x18008970d  mov     ebx, 80004001h
0x180089712  mov     edx, 0E8h; void *
0x180089717  mov     rcx, [rsp+88h]; this
0x18008971f  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180089726  mov     r9d, ebx; char *
0x180089729  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008972e  mov     eax, ebx
0x180089730  jmp     loc_1800897E0
0x180089735  mov     eax, [rsp+88h+arg_60]
0x18008973c  mov     r8d, edi
0x18008973f  mov     r9d, [rsp+88h+arg_20]
0x180089747  mov     edx, esi
0x180089749  mov     [rsp+88h+var_30], eax
0x18008974d  mov     ecx, ebp
0x18008974f  mov     eax, [rsp+88h+arg_58]
0x180089756  mov     [rsp+88h+var_38], eax
0x18008975a  mov     rax, [rsp+88h+arg_50]
0x180089762  mov     [rsp+88h+var_40], rax
0x180089767  mov     eax, [rsp+88h+arg_48]
0x18008976e  mov     [rsp+88h+var_48], eax
0x180089772  mov     eax, [rsp+88h+arg_40]
0x180089779  mov     [rsp+88h+var_50], eax
0x18008977d  mov     rax, [rsp+88h+arg_38]
0x180089785  mov     [rsp+88h+var_58], rax
0x18008978a  mov     eax, [rsp+88h+arg_30]
0x180089791  mov     [rsp+88h+var_60], eax
0x180089795  mov     eax, [rsp+88h+arg_28]
0x18008979c  mov     [rsp+88h+var_68], eax
0x1800897a0  mov     qword ptr [rbx+48h], 2
0x1800897a8  call    cs:__imp_CreateCursorFromBitmap
0x1800897ae  mov     [rbx+50h], rax
0x1800897b2  test    rax, rax
0x1800897b5  jnz     short loc_1800897DE
0x1800897b7  call    cs:__imp_GetLastError
0x1800897bd  mov     ebx, eax
0x1800897bf  test    eax, eax
0x1800897c1  jle     short loc_1800897CC
0x1800897c3  movzx   ebx, ax
0x1800897c6  or      ebx, 80070000h
0x1800897cc  test    ebx, ebx
0x1800897ce  jns     loc_18008972E
0x1800897d4  mov     edx, 0FBh
0x1800897d9  jmp     loc_180089717
0x1800897de  xor     eax, eax
0x1800897e0  add     rsp, 68h
0x1800897e4  pop     rdi
0x1800897e5  pop     rsi
0x1800897e6  pop     rbp
0x1800897e7  pop     rbx
0x1800897e8  retn
```
