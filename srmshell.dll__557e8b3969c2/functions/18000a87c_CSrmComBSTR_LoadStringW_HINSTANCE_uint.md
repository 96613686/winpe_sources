# CSrmComBSTR::LoadStringW(HINSTANCE__ *,uint)

- ea: `0x18000a87c`
- end: `0x18000a902`
- name: `?LoadStringW@CSrmComBSTR@@QEAA_NPEAUHINSTANCE__@@I@Z`
- size: `134`
- prototype: `bool __fastcall(BSTR *this, HINSTANCE, UINT)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007290`
- `0x180008408`
- `0x18000ace8`
- `0x18000b668`
- `0x18000c8b0`
- `0x18000ca10`
- `0x18000ce98`
- `0x18000d880`
- `0x18000db28`
- `0x18000f7cc`
- `0x18000f910`

## callees

- `0x18000a87c`
- `0x18001b420`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a8cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a8cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a8c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a8c0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a8b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a8b5`

## pseudocode

```c
bool __fastcall CSrmComBSTR::LoadStringW(BSTR *this, HINSTANCE a2, UINT a3)
{
  int StringW; // edi
  BSTR v5; // rax
  WCHAR Buffer[512]; // [rsp+20h] [rbp-418h] BYREF

  StringW = LoadStringW(a2, a3, Buffer, 512);
  SysFreeString(*this);
  if ( StringW )
    v5 = SysAllocString(Buffer);
  else
    v5 = 0;
  *this = v5;
  return StringW != 0;
}

```

## disassembly

```asm
0x18000a87c  mov     [rsp+arg_18], rbx
0x18000a881  push    rdi
0x18000a882  sub     rsp, 430h
0x18000a889  mov     rax, cs:__security_cookie
0x18000a890  xor     rax, rsp
0x18000a893  mov     [rsp+438h+var_18], rax
0x18000a89b  mov     r10d, r8d
0x18000a89e  mov     rax, rdx
0x18000a8a1  mov     rbx, rcx
0x18000a8a4  lea     r8, [rsp+438h+Buffer]; lpBuffer
0x18000a8a9  mov     edx, r10d; uID
0x18000a8ac  mov     rcx, rax; hInstance
0x18000a8af  mov     r9d, 200h; cchBufferMax
0x18000a8b5  call    cs:__imp_LoadStringW
0x18000a8bb  mov     rcx, [rbx]; bstrString
0x18000a8be  mov     edi, eax
0x18000a8c0  call    cs:__imp_SysFreeString
0x18000a8c6  test    edi, edi
0x18000a8c8  jz      short loc_18000A8D7
0x18000a8ca  lea     rcx, [rsp+438h+Buffer]; psz
0x18000a8cf  call    cs:__imp_SysAllocString
0x18000a8d5  jmp     short loc_18000A8D9
0x18000a8d7  xor     eax, eax
0x18000a8d9  test    edi, edi
0x18000a8db  mov     [rbx], rax
0x18000a8de  setnz   al
0x18000a8e1  mov     rcx, [rsp+438h+var_18]
0x18000a8e9  xor     rcx, rsp; StackCookie
0x18000a8ec  call    __security_check_cookie
0x18000a8f1  mov     rbx, [rsp+438h+arg_18]
0x18000a8f9  add     rsp, 430h
0x18000a900  pop     rdi
0x18000a901  retn
```
