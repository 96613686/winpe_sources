# SpeechPlatform::Settings::Details::RegistryStorage<HSTRING__ *>::GetValue(HKEY__ * const,ushort const * const,ushort const * const,HSTRING__ * &)

- ea: `0x1801708e4`
- end: `0x180170a08`
- name: `?GetValue@?$RegistryStorage@PEAUHSTRING__@@@Details@Settings@SpeechPlatform@@SAJQEAUHKEY__@@QEBG1AEAPEAUHSTRING__@@@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1801701ac`

## callees

- `0x1801708e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180170924`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18017098f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180170924`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18017098f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801709ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801709ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801709d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801709d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801709f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801709f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18017094d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18017094d`

## pseudocode

```c
__int64 __fastcall SpeechPlatform::Settings::Details::RegistryStorage<HSTRING__ *>::GetValue(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        HSTRING *a4)
{
  LSTATUS ValueW; // eax
  int v8; // ebx
  HLOCAL pvData; // rdi
  LSTATUS v10; // eax
  unsigned __int64 v11; // rdx
  HSTRING string; // [rsp+40h] [rbp-48h] BYREF
  DWORD uBytes; // [rsp+90h] [rbp+8h] BYREF
  int uBytes_4; // [rsp+94h] [rbp+Ch]

  uBytes_4 = HIDWORD(a1);
  uBytes = 0;
  ValueW = RegGetValueW(HKEY_CURRENT_USER, a2, a3, 0x10002u, 0, 0, &uBytes);
  v8 = ValueW;
  if ( ValueW > 0 )
    v8 = (unsigned __int16)ValueW | 0x80070000;
  if ( v8 >= 0 )
  {
    pvData = LocalAlloc(0x40u, uBytes);
    if ( pvData )
    {
      v10 = RegGetValueW(HKEY_CURRENT_USER, a2, a3, 0x10002u, 0, pvData, &uBytes);
      v8 = v10;
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      if ( v8 >= 0 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *((_WORD *)pvData + v11) );
        if ( v11 < 0xFFFFFFFF )
        {
          string = 0;
          v8 = WindowsCreateString((PCNZWCH)pvData, v11, &string);
          if ( v8 < 0 )
            WindowsDeleteString(string);
          else
            *a4 = string;
        }
        else
        {
          v8 = -2147467259;
        }
        LocalFree(pvData);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801708e4  mov     r11, rsp
0x1801708e7  mov     [r11+8], rcx
0x1801708eb  push    rbx
0x1801708ec  push    rbp
0x1801708ed  push    rsi
0x1801708ee  push    rdi
0x1801708ef  push    r14
0x1801708f1  push    r15
0x1801708f3  sub     rsp, 58h
0x1801708f7  xor     r15d, r15d
0x1801708fa  lea     rax, [r11+8]
0x1801708fe  mov     [r11-58h], rax
0x180170902  mov     r14, r9
0x180170905  mov     [r11-60h], r15
0x180170909  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180170910  mov     r9d, 10002h; dwFlags
0x180170916  mov     [r11-68h], r15
0x18017091a  mov     rsi, r8
0x18017091d  mov     [r11+8], r15d
0x180170921  mov     rbp, rdx
0x180170924  call    cs:__imp_RegGetValueW
0x18017092a  mov     ebx, eax
0x18017092c  test    eax, eax
0x18017092e  jle     short loc_180170939
0x180170930  movzx   ebx, ax
0x180170933  or      ebx, 80070000h
0x180170939  test    ebx, ebx
0x18017093b  js      loc_1801709F9
0x180170941  mov     edx, dword ptr [rsp+88h+uBytes]; uBytes
0x180170948  mov     ecx, 40h ; '@'; uFlags
0x18017094d  call    cs:__imp_LocalAlloc
0x180170953  mov     rdi, rax
0x180170956  test    rax, rax
0x180170959  jnz     short loc_180170965
0x18017095b  mov     ebx, 8007000Eh
0x180170960  jmp     loc_1801709F9
0x180170965  lea     rax, [rsp+88h+uBytes]
0x18017096d  mov     r9d, 10002h; dwFlags
0x180170973  mov     [rsp+88h+pcbData], rax; pcbData
0x180170978  mov     r8, rsi; lpValue
0x18017097b  mov     [rsp+88h+pvData], rdi; pvData
0x180170980  mov     rdx, rbp; lpSubKey
0x180170983  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18017098a  mov     [rsp+88h+pdwType], r15; pdwType
0x18017098f  call    cs:__imp_RegGetValueW
0x180170995  mov     ebx, eax
0x180170997  test    eax, eax
0x180170999  jle     short loc_1801709A4
0x18017099b  movzx   ebx, ax
0x18017099e  or      ebx, 80070000h
0x1801709a4  test    ebx, ebx
0x1801709a6  js      short loc_1801709F9
0x1801709a8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801709ac  inc     rdx; length
0x1801709af  cmp     [rdi+rdx*2], r15w
0x1801709b4  jnz     short loc_1801709AC
0x1801709b6  mov     eax, 0FFFFFFFFh
0x1801709bb  cmp     rdx, rax
0x1801709be  jb      short loc_1801709C7
0x1801709c0  mov     ebx, 80004005h
0x1801709c5  jmp     short loc_1801709F0
0x1801709c7  lea     r8, [rsp+88h+string]; string
0x1801709cc  mov     [rsp+88h+string], r15
0x1801709d1  mov     rcx, rdi; sourceString
0x1801709d4  call    cs:__imp_WindowsCreateString
0x1801709da  mov     rcx, [rsp+88h+string]; string
0x1801709df  mov     ebx, eax
0x1801709e1  test    eax, eax
0x1801709e3  js      short loc_1801709EA
0x1801709e5  mov     [r14], rcx
0x1801709e8  jmp     short loc_1801709F0
0x1801709ea  call    cs:__imp_WindowsDeleteString
0x1801709f0  mov     rcx, rdi; hMem
0x1801709f3  call    cs:__imp_LocalFree
0x1801709f9  mov     eax, ebx
0x1801709fb  add     rsp, 58h
0x1801709ff  pop     r15
0x180170a01  pop     r14
0x180170a03  pop     rdi
0x180170a04  pop     rsi
0x180170a05  pop     rbp
0x180170a06  pop     rbx
0x180170a07  retn
```
