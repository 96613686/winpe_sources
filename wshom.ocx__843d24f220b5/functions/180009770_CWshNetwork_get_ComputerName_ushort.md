# CWshNetwork::get_ComputerName(ushort * *)

- ea: `0x180009770`
- end: `0x18000983d`
- name: `?get_ComputerName@CWshNetwork@@UEAAJPEAPEAG@Z`
- size: `205`
- prototype: `__int64 __fastcall(CWshNetwork *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009770`
- `0x180010250`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000980b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000980b`
- `KERNEL32!GetLastError` at `0x1800097bc`
- `KERNEL32!GetLastError` at `0x1800097bc`
- `KERNEL32!MultiByteToWideChar` at `0x1800097fe`
- `KERNEL32!MultiByteToWideChar` at `0x1800097fe`
- `KERNEL32!GetComputerNameW` at `0x1800097b2`
- `KERNEL32!GetComputerNameW` at `0x1800097b2`
- `KERNEL32!GetComputerNameA` at `0x1800097d5`
- `KERNEL32!GetComputerNameA` at `0x1800097d5`

## pseudocode

```c
signed int __fastcall CWshNetwork::get_ComputerName(CWshNetwork *this, unsigned __int16 **a2)
{
  signed int result; // eax
  int ComputerNameW; // eax
  unsigned __int16 *v5; // rcx
  DWORD nSize; // [rsp+30h] [rbp-48h] BYREF
  CHAR MultiByteStr[16]; // [rsp+38h] [rbp-40h] BYREF
  WCHAR Buffer[16]; // [rsp+48h] [rbp-30h] BYREF

  if ( !a2 )
    return -2147467261;
  nSize = 16;
  if ( Global::g_fWindowsNT )
  {
    ComputerNameW = GetComputerNameW(Buffer, &nSize);
  }
  else
  {
    if ( !GetComputerNameA(MultiByteStr, &nSize) )
    {
LABEL_6:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    ComputerNameW = MultiByteToWideChar(0, 0, MultiByteStr, -1, Buffer, 16);
  }
  if ( !ComputerNameW )
    goto LABEL_6;
  v5 = SysAllocString(Buffer);
  *a2 = v5;
  result = 0;
  if ( nSize && !v5 )
    return -2147024882;
  return result;
}

```

## disassembly

```asm
0x180009770  push    rbx
0x180009772  sub     rsp, 70h
0x180009776  mov     rax, cs:__security_cookie
0x18000977d  xor     rax, rsp
0x180009780  mov     [rsp+78h+var_10], rax
0x180009785  mov     rbx, rdx
0x180009788  test    rdx, rdx
0x18000978b  jnz     short loc_180009797
0x18000978d  mov     eax, 80004003h
0x180009792  jmp     loc_18000982A
0x180009797  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000979e  lea     rdx, [rsp+78h+nSize]; nSize
0x1800097a3  mov     [rsp+78h+nSize], 10h
0x1800097ab  jz      short loc_1800097D0
0x1800097ad  lea     rcx, [rsp+78h+Buffer]; lpBuffer
0x1800097b2  call    cs:__imp_GetComputerNameW
0x1800097b8  test    eax, eax
0x1800097ba  jnz     short loc_180009806
0x1800097bc  call    cs:__imp_GetLastError
0x1800097c2  test    eax, eax
0x1800097c4  jle     short loc_18000982A
0x1800097c6  movzx   eax, ax
0x1800097c9  or      eax, 80070000h
0x1800097ce  jmp     short loc_18000982A
0x1800097d0  lea     rcx, [rsp+78h+MultiByteStr]; lpBuffer
0x1800097d5  call    cs:__imp_GetComputerNameA
0x1800097db  test    eax, eax
0x1800097dd  jz      short loc_1800097BC
0x1800097df  lea     rax, [rsp+78h+Buffer]
0x1800097e4  mov     [rsp+78h+cchWideChar], 10h; cchWideChar
0x1800097ec  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800097f0  mov     [rsp+78h+lpWideCharStr], rax; lpWideCharStr
0x1800097f5  lea     r8, [rsp+78h+MultiByteStr]; lpMultiByteStr
0x1800097fa  xor     edx, edx; dwFlags
0x1800097fc  xor     ecx, ecx; CodePage
0x1800097fe  call    cs:__imp_MultiByteToWideChar
0x180009804  jmp     short loc_1800097B8
0x180009806  lea     rcx, [rsp+78h+Buffer]; psz
0x18000980b  call    cs:__imp_SysAllocString
0x180009811  mov     rcx, rax
0x180009814  mov     [rbx], rax
0x180009817  xor     eax, eax
0x180009819  cmp     [rsp+78h+nSize], eax
0x18000981d  jz      short loc_18000982A
0x18000981f  test    rcx, rcx
0x180009822  mov     edx, 8007000Eh
0x180009827  cmovz   eax, edx
0x18000982a  mov     rcx, [rsp+78h+var_10]
0x18000982f  xor     rcx, rsp; StackCookie
0x180009832  call    __security_check_cookie
0x180009837  add     rsp, 70h
0x18000983b  pop     rbx
0x18000983c  retn
```
