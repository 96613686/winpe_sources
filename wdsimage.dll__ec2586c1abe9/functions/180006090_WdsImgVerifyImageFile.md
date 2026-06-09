# WdsImgVerifyImageFile

- ea: `0x180006090`
- end: `0x1800061b5`
- name: `WdsImgVerifyImageFile`
- size: `293`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800039a8`
- `0x180003a60`
- `0x180003c68`
- `0x180003d64`
- `0x180006090`
- `0x18000ae64`
- `0x18000ff10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006145`
- `KERNEL32!GetLastError` at `0x180006145`
- `WIMGAPI!WIMCloseHandle` at `0x18000617b`
- `WIMGAPI!WIMCloseHandle` at `0x18000617b`
- `WIMGAPI!WIMCreateFile` at `0x180006134`
- `WIMGAPI!WIMCreateFile` at `0x180006134`

## pseudocode

```c
__int64 __fastcall WdsImgVerifyImageFile(unsigned __int16 *a1, int a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rax
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  _DWORD v13[4]; // [rsp+30h] [rbp-1B8h] BYREF
  _BYTE v14[28]; // [rsp+40h] [rbp-1A8h] BYREF
  int v15; // [rsp+5Ch] [rbp-18Ch]

  v13[0] = 0;
  CImage::CImage((CImage *)v14);
  if ( a1 )
  {
    if ( a2 )
    {
      LODWORD(v4) = -1056833009;
    }
    else
    {
      v4 = (unsigned int)CImage::Initialize((CImage *)v14, a1, 1, 144);
      if ( (int)ElValidateHr_0(v4, v5, v6, 2015) >= 0 && v15 == 2 )
      {
        v7 = WIMCreateFile(a1, 0x80000000LL, 3, 2, 0, v13);
        if ( v7 )
        {
          WIMCloseHandle(v7);
        }
        else
        {
          LastError = GetLastError();
          v11 = ElValidateWin32(LastError, v9, v10, 2031);
          LODWORD(v4) = v11;
          if ( v11 > 0 )
            LODWORD(v4) = (unsigned __int16)v11 | 0x80070000;
          if ( (int)v4 >= 0 )
            LODWORD(v4) = -2147467259;
        }
      }
    }
  }
  else
  {
    LODWORD(v4) = -2147024809;
  }
  CImage::~CImage((CImage *)v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006090  mov     [rsp+arg_10], rbx
0x180006095  push    rdi
0x180006096  sub     rsp, 1E0h
0x18000609d  mov     rax, cs:__security_cookie
0x1800060a4  xor     rax, rsp
0x1800060a7  mov     [rsp+1E8h+var_18], rax
0x1800060af  and     [rsp+1E8h+var_1B8], 0
0x1800060b4  mov     rdi, rcx
0x1800060b7  lea     rcx, [rsp+1E8h+var_1A8]; this
0x1800060bc  mov     ebx, edx
0x1800060be  call    ??0CImage@@QEAA@XZ; CImage::CImage(void)
0x1800060c3  test    rdi, rdi
0x1800060c6  jnz     short loc_1800060D2
0x1800060c8  mov     ebx, 80070057h
0x1800060cd  jmp     loc_180006187
0x1800060d2  test    ebx, ebx
0x1800060d4  jz      short loc_1800060E0
0x1800060d6  mov     ebx, 0C102020Fh
0x1800060db  jmp     loc_180006187
0x1800060e0  mov     r9d, 90h; unsigned int
0x1800060e6  lea     rcx, [rsp+1E8h+var_1A8]; this
0x1800060eb  mov     r8d, 1; unsigned int
0x1800060f1  mov     rdx, rdi; unsigned __int16 *
0x1800060f4  call    ?Initialize@CImage@@QEAAJPEBGKK@Z; CImage::Initialize(ushort const *,ulong,ulong)
0x1800060f9  mov     r9d, 7DFh
0x1800060ff  mov     ecx, eax
0x180006101  mov     ebx, eax
0x180006103  call    ElValidateHr_0
0x180006108  test    eax, eax
0x18000610a  js      short loc_180006187
0x18000610c  mov     r9d, 2
0x180006112  cmp     [rsp+1E8h+var_18C], r9d
0x180006117  jnz     short loc_180006187
0x180006119  lea     rax, [rsp+1E8h+var_1B8]
0x18000611e  mov     edx, 80000000h
0x180006123  mov     [rsp+1E8h+var_1C0], rax
0x180006128  lea     r8d, [r9+1]
0x18000612c  and     [rsp+1E8h+var_1C8], 0
0x180006131  mov     rcx, rdi
0x180006134  call    cs:__imp_WIMCreateFile
0x18000613b  nop     dword ptr [rax+rax+00h]
0x180006140  test    rax, rax
0x180006143  jnz     short loc_180006178
0x180006145  call    cs:__imp_GetLastError
0x18000614c  nop     dword ptr [rax+rax+00h]
0x180006151  mov     ecx, eax
0x180006153  mov     r9d, 7EFh
0x180006159  call    ElValidateWin32
0x18000615e  mov     ebx, eax
0x180006160  test    eax, eax
0x180006162  jle     short loc_18000616D
0x180006164  movzx   ebx, ax
0x180006167  or      ebx, 80070000h
0x18000616d  test    ebx, ebx
0x18000616f  js      short loc_180006187
0x180006171  mov     ebx, 80004005h
0x180006176  jmp     short loc_180006187
0x180006178  mov     rcx, rax
0x18000617b  call    cs:__imp_WIMCloseHandle
0x180006182  nop     dword ptr [rax+rax+00h]
0x180006187  lea     rcx, [rsp+1E8h+var_1A8]; this
0x18000618c  call    ??1CImage@@UEAA@XZ; CImage::~CImage(void)
0x180006191  mov     eax, ebx
0x180006193  mov     rcx, [rsp+1E8h+var_18]
0x18000619b  xor     rcx, rsp; StackCookie
0x18000619e  call    __security_check_cookie
0x1800061a3  mov     rbx, [rsp+1E8h+arg_10]
0x1800061ab  add     rsp, 1E0h
0x1800061b2  pop     rdi
0x1800061b3  retn
```
