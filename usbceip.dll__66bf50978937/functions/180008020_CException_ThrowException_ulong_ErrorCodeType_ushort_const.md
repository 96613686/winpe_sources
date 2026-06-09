# CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)

- ea: `0x180008020`
- end: `0x1800080b0`
- name: `?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ`
- size: `144`
- prototype: `void __noreturn(unsigned int, unsigned int, const wchar_t *, ...)`
- caller_count: `31`
- callee_count: `4`
- tags: ``

## callers

- `0x1800064b0`
- `0x1800072b4`
- `0x1800074fc`
- `0x1800075e4`
- `0x1800079c0`
- `0x1800081a0`
- `0x18000823c`
- `0x180008290`
- `0x180008730`
- `0x180008c74`
- `0x180009520`
- `0x180009630`
- `0x18000a4c8`
- `0x18000a590`
- `0x18000a618`
- `0x18000a698`
- `0x18000a838`
- `0x18000aa38`
- `0x18000ab84`
- `0x18000af00`
- `0x18000af94`
- `0x18000b358`
- `0x18000b464`
- `0x18000b5c8`
- `0x18000b78c`
- `0x18000bc7c`
- `0x18000be14`
- `0x18000bebc`
- `0x18000c114`
- `0x18000c16c`
- `0x18000c4d0`

## callees

- `0x180002e7a`
- `0x180002e88`
- `0x180007aa8`
- `0x180008020`

## pseudocode

```c
void __noreturn CException::ThrowException(unsigned int a1, unsigned int a2, const wchar_t *a3, ...)
{
  unsigned __int64 pExceptionObject; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v6[8]; // [rsp+28h] [rbp-830h] BYREF
  wchar_t Buffer[1024]; // [rsp+30h] [rbp-828h] BYREF
  va_list va; // [rsp+878h] [rbp+20h] BYREF

  va_start(va, a3);
  pExceptionObject = 0;
  Buffer[0] = 0;
  if ( a3 )
  {
    if ( (unsigned int)vsnwprintf(Buffer, 0x3FFu, a3, va) > 0x3FE )
      Buffer[1023] = 0;
  }
  pExceptionObject = __PAIR64__(a2, a1);
  _bstr_t::_bstr_t((_bstr_t *)v6, Buffer);
  throw (CException *)&pExceptionObject;
}

```

## disassembly

```asm
0x180008020  mov     r11, rsp
0x180008023  mov     [r11+18h], r8
0x180008027  mov     [r11+20h], r9
0x18000802b  push    rbx
0x18000802c  push    rdi
0x18000802d  sub     rsp, 848h
0x180008034  mov     rax, cs:__security_cookie
0x18000803b  xor     rax, rsp
0x18000803e  mov     [rsp+858h+var_28], rax
0x180008046  xor     eax, eax
0x180008048  mov     [rsp+858h+pExceptionObject], 0
0x180008051  mov     [rsp+858h+Buffer], ax
0x180008056  mov     ebx, edx
0x180008058  mov     edi, ecx
0x18000805a  test    r8, r8
0x18000805d  jz      short loc_180008087
0x18000805f  lea     r9, [r11+20h]; Args
0x180008063  mov     edx, 3FFh; BufferCount
0x180008068  lea     rcx, [rsp+858h+Buffer]; Buffer
0x18000806d  call    _vsnwprintf
0x180008072  test    eax, eax
0x180008074  js      short loc_18000807D
0x180008076  cmp     eax, 3FFh
0x18000807b  jb      short loc_180008087
0x18000807d  xor     eax, eax
0x18000807f  mov     [rsp+858h+var_2A], ax
0x180008087  lea     rdx, [rsp+858h+Buffer]; unsigned __int16 *
0x18000808c  mov     dword ptr [rsp+858h+pExceptionObject], edi
0x180008090  lea     rcx, [rsp+858h+var_830]; this
0x180008095  mov     dword ptr [rsp+858h+pExceptionObject+4], ebx
0x180008099  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000809e  lea     rdx, _TI1?AVCException@@; pThrowInfo
0x1800080a5  lea     rcx, [rsp+858h+pExceptionObject]; pExceptionObject
0x1800080aa  call    _CxxThrowException_0
```
