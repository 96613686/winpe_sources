# CHost::ReportLoadError(long)

- ea: `0x14000cf0c`
- end: `0x14000cfb3`
- name: `?ReportLoadError@CHost@@QEAAJJ@Z`
- size: `167`
- prototype: `int(CHost *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000757c`
- `0x140007dc8`
- `0x14000c740`

## callees

- `0x140009b54`
- `0x14000cf0c`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000cfa0`
- `OLEAUT32!__imp_SysFreeString` at `0x14000cfa0`

## pseudocode

```c
__int64 __fastcall CHost::ReportLoadError(CHost *this, DWORD a2)
{
  OLECHAR *v2; // rbx
  __int64 result; // rax
  unsigned int v5; // eax
  unsigned int v6; // edi
  BSTR bstrString; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  result = 2147811327LL;
  bstrString = 0;
  if ( a2 != -2147155969 && a2 != -2147352319 )
  {
    if ( a2 + 2147024894 <= 1 )
    {
      v5 = (*(__int64 (__fastcall **)(CHost *, _QWORD, __int64, _QWORD, const OLECHAR *))(*(_QWORD *)this + 8LL))(
             this,
             (unsigned int)(Global::g_lResourceBase + 21),
             3310,
             *((_QWORD *)this + 76),
             &Default);
    }
    else
    {
      FormatHResult(a2, &bstrString);
      v2 = bstrString;
      v5 = (*(__int64 (__fastcall **)(CHost *, _QWORD, __int64, _QWORD, BSTR))(*(_QWORD *)this + 8LL))(
             this,
             (unsigned int)(Global::g_lResourceBase + 20),
             3204,
             *((_QWORD *)this + 76),
             bstrString);
    }
    v6 = v5;
    SysFreeString(v2);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14000cf0c  mov     [rsp+arg_0], rbx
0x14000cf11  push    rdi
0x14000cf12  sub     rsp, 30h
0x14000cf16  xor     ebx, ebx
0x14000cf18  mov     eax, 8004FFFFh
0x14000cf1d  mov     [rsp+38h+bstrString], rbx
0x14000cf22  mov     r8d, edx
0x14000cf25  mov     rdi, rcx
0x14000cf28  cmp     edx, eax
0x14000cf2a  jz      short loc_14000CFA8
0x14000cf2c  cmp     edx, 80020101h
0x14000cf32  jz      short loc_14000CFA8
0x14000cf34  lea     eax, [rdx+7FF8FFFEh]
0x14000cf3a  cmp     eax, 1
0x14000cf3d  jbe     short loc_14000CF6A
0x14000cf3f  lea     rdx, [rsp+38h+bstrString]; unsigned __int16 **
0x14000cf44  mov     ecx, r8d; dwMessageId
0x14000cf47  call    ?FormatHResult@@YAJJPEAPEAG@Z; FormatHResult(long,ushort * *)
0x14000cf4c  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x14000cf52  mov     r8d, 0C84h
0x14000cf58  mov     rbx, [rsp+38h+bstrString]
0x14000cf5d  add     edx, 14h
0x14000cf60  mov     rax, [rdi]
0x14000cf63  mov     [rsp+38h+var_18], rbx
0x14000cf68  jmp     short loc_14000CF88
0x14000cf6a  mov     rax, [rcx]
0x14000cf6d  mov     r8d, 0CEEh
0x14000cf73  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x14000cf79  lea     rcx, Default
0x14000cf80  mov     [rsp+38h+var_18], rcx
0x14000cf85  add     edx, 15h
0x14000cf88  mov     r9, [rdi+260h]
0x14000cf8f  mov     rcx, rdi
0x14000cf92  mov     rax, [rax+8]
0x14000cf96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf9b  mov     rcx, rbx; bstrString
0x14000cf9e  mov     edi, eax
0x14000cfa0  call    cs:__imp_SysFreeString
0x14000cfa6  mov     eax, edi
0x14000cfa8  mov     rbx, [rsp+38h+arg_0]
0x14000cfad  add     rsp, 30h
0x14000cfb1  pop     rdi
0x14000cfb2  retn
```
