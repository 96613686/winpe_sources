# CTooltip::UpdateTipText(HWND__ *,uint,char *)

- ea: `0x180022b40`
- end: `0x180022c6e`
- name: `?UpdateTipText@CTooltip@@QEBAXPEAUHWND__@@IPEAD@Z`
- size: `302`
- prototype: `void(CTooltip *__hidden this, HWND, unsigned int, char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180020ab0`
- `0x180022af4`

## callees

- `0x1800036ac`
- `0x1800036fc`
- `0x180008484`
- `0x180022b40`
- `0x18002d840`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180022bb4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180022bb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022bd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022bd3`
- `USER32!SendMessageW` at `0x180022c3d`
- `USER32!SendMessageW` at `0x180022c3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CTooltip::UpdateTipText(CTooltip *this, LPARAM a2, UINT a3, va_list a4)
{
  WCHAR Buffer[4]; // [rsp+40h] [rbp-39h] BYREF
  LPCVOID lpSource; // [rsp+48h] [rbp-31h] BYREF
  const unsigned __int16 *v8; // [rsp+50h] [rbp-29h] BYREF
  va_list Arguments; // [rsp+58h] [rbp-21h] BYREF
  LPARAM lParam[10]; // [rsp+60h] [rbp-19h] BYREF

  Arguments = a4;
  v8 = WTL::_atltmpPchNil;
  *(_QWORD *)Buffer = 0;
  lpSource = WTL::_atltmpPchNil;
  WTL::CString::LoadStringW((WTL::CString *)&lpSource, a3);
  if ( FormatMessageW(0x500u, lpSource, 0, 0, Buffer, 0, &Arguments) )
  {
    WTL::CString::operator=((WTL::CString *)&v8, *(unsigned __int16 **)Buffer);
    LocalFree(*(HLOCAL *)Buffer);
    *(_QWORD *)Buffer = 0;
    lParam[3] = 0;
    lParam[4] = 0;
    lParam[7] = 0;
    lParam[8] = 0;
    lParam[0] = 0x11100000048LL;
    lParam[1] = *((_QWORD *)this + 1);
    lParam[2] = a2;
    lParam[5] = (LPARAM)hInstance;
    lParam[6] = (LPARAM)v8;
    SendMessageW(*(HWND *)this, 0x439u, 0, (LPARAM)lParam);
  }
  WTL::CString::~CString((WTL::CString *)&lpSource);
  WTL::CString::~CString((WTL::CString *)&v8);
}

```

## disassembly

```asm
0x180022b40  push    rbp
0x180022b42  push    rbx
0x180022b43  push    rdi
0x180022b44  lea     rbp, [rsp-47h]
0x180022b49  sub     rsp, 0C0h
0x180022b50  mov     rax, cs:__security_cookie
0x180022b57  xor     rax, rsp
0x180022b5a  mov     [rbp+57h+var_20], rax
0x180022b5e  mov     rdi, rdx
0x180022b61  mov     rbx, rcx
0x180022b64  mov     [rbp+57h+var_78], r9
0x180022b68  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x180022b6f  mov     [rbp+57h+var_80], rax
0x180022b73  mov     qword ptr [rbp+57h+Buffer], 0
0x180022b7b  mov     [rbp+57h+lpSource], rax
0x180022b7f  mov     edx, r8d; uID
0x180022b82  lea     rcx, [rbp+57h+lpSource]; this
0x180022b86  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x180022b8b  lea     rax, [rbp+57h+var_78]
0x180022b8f  mov     [rsp+0D0h+Arguments], rax; Arguments
0x180022b94  mov     [rsp+0D0h+nSize], 0; nSize
0x180022b9c  lea     rax, [rbp+57h+Buffer]
0x180022ba0  mov     [rsp+0D0h+lpBuffer], rax; lpBuffer
0x180022ba5  xor     r9d, r9d; dwLanguageId
0x180022ba8  xor     r8d, r8d; dwMessageId
0x180022bab  mov     rdx, [rbp+57h+lpSource]; lpSource
0x180022baf  mov     ecx, 500h; dwFlags
0x180022bb4  call    cs:__imp_FormatMessageW
0x180022bba  test    eax, eax
0x180022bbc  jz      loc_180022C44
0x180022bc2  mov     rdx, qword ptr [rbp+57h+Buffer]; unsigned __int16 *
0x180022bc6  lea     rcx, [rbp+57h+var_80]; this
0x180022bca  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x180022bcf  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x180022bd3  call    cs:__imp_LocalFree
0x180022bd9  mov     qword ptr [rbp+57h+Buffer], 0
0x180022be1  mov     [rbp+57h+var_58], 0
0x180022be9  mov     [rbp+57h+var_50], 0
0x180022bf1  mov     [rbp+57h+var_38], 0
0x180022bf9  mov     [rbp+57h+var_30], 0
0x180022c01  mov     dword ptr [rbp+57h+lParam], 48h ; 'H'
0x180022c08  mov     dword ptr [rbp+57h+lParam+4], 111h
0x180022c0f  mov     rax, [rbx+8]
0x180022c13  mov     [rbp+57h+var_68], rax
0x180022c17  mov     [rbp+57h+var_60], rdi
0x180022c1b  mov     rax, cs:hInstance
0x180022c22  mov     [rbp+57h+var_48], rax
0x180022c26  mov     rax, [rbp+57h+var_80]
0x180022c2a  mov     [rbp+57h+var_40], rax
0x180022c2e  lea     r9, [rbp+57h+lParam]; lParam
0x180022c32  xor     r8d, r8d; wParam
0x180022c35  mov     edx, 439h; Msg
0x180022c3a  mov     rcx, [rbx]; hWnd
0x180022c3d  call    cs:__imp_SendMessageW
0x180022c43  nop
0x180022c44  lea     rcx, [rbp+57h+lpSource]; this
0x180022c48  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180022c4d  nop
0x180022c4e  lea     rcx, [rbp+57h+var_80]; this
0x180022c52  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180022c57  mov     rcx, [rbp+57h+var_20]
0x180022c5b  xor     rcx, rsp; StackCookie
0x180022c5e  call    __security_check_cookie
0x180022c63  add     rsp, 0C0h
0x180022c6a  pop     rdi
0x180022c6b  pop     rbx
0x180022c6c  pop     rbp
0x180022c6d  retn
```
