# RecordFileVersion(void)

- ea: `0x180011d44`
- end: `0x180011f38`
- name: `?RecordFileVersion@@YAXXZ`
- size: `500`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180010efc`

## callees

- `0x180005f7c`
- `0x1800074c8`
- `0x1800074d4`
- `0x18000c8f4`
- `0x180011d44`
- `0x18002c520`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180011dd8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180011e5d`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180011dd8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180011e5d`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180011da9`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180011da9`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180011d6b`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180011d6b`

## string_xrefs

- `0x180011d5f`: `schedsvc.dll`
- `0x180011d95`: `schedsvc.dll`

## pseudocode

```c
void RecordFileVersion(void)
{
  DWORD FileVersionInfoSize; // eax
  DWORD v1; // edi
  unsigned __int64 v2; // r15
  void *v3; // rax
  void *v4; // rbx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // r14
  __int64 v7; // rdi
  unsigned int v8; // eax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rsi
  LPVOID lpData; // [rsp+20h] [rbp-28h]
  LPVOID lpBuffer; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v13; // [rsp+80h] [rbp+38h] BYREF
  unsigned int puLen; // [rsp+88h] [rbp+40h] BYREF
  DWORD dwHandle; // [rsp+90h] [rbp+48h] BYREF
  LPVOID v16; // [rsp+98h] [rbp+50h] BYREF

  dwHandle = 0;
  FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, L"schedsvc.dll", &dwHandle);
  v1 = FileVersionInfoSize;
  if ( FileVersionInfoSize )
  {
    v2 = FileVersionInfoSize;
    v3 = operator new[](FileVersionInfoSize);
    v4 = v3;
    if ( v3 )
    {
      if ( GetFileVersionInfoExW(3u, L"schedsvc.dll", dwHandle, v1, v3) )
      {
        lpBuffer = 0;
        puLen = 0;
        if ( VerQueryValueW(v4, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen) )
        {
          v5 = (unsigned __int16 *)operator new[](saturated_mul(v1, 2u));
          v16 = 0;
          v6 = v5;
          v13 = 0;
          if ( v5 )
          {
            v7 = 0;
            if ( (puLen & 0xFFFFFFFC) != 0 )
            {
              do
              {
                LODWORD(lpData) = *((unsigned __int16 *)lpBuffer + 2 * v7 + 1);
                StringCchPrintfW(
                  v6,
                  v2,
                  L"\\StringFileInfo\\%04x%04x\\FileVersion",
                  *((unsigned __int16 *)lpBuffer + 2 * v7),
                  lpData);
                if ( VerQueryValueW(v4, v6, &v16, &v13) )
                {
                  v8 = v13;
                  if ( v13 )
                  {
                    if ( v13 >= 0x100 )
                      v8 = 256;
                    v13 = v8 + 2;
                    v9 = (unsigned __int16 *)operator new[](saturated_mul(v8 + 2, 2u));
                    v10 = v9;
                    if ( v9 )
                    {
                      StringCchPrintfW(v9, v13, L"%s\r\n", v16);
                      LogServiceMessage(v10, v13);
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                      {
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          41,
                          WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
                          v16);
                      }
                      operator delete(v10);
                    }
                  }
                }
                v7 = (unsigned int)(v7 + 1);
              }
              while ( (unsigned int)v7 < puLen >> 2 );
            }
            operator delete(v6);
          }
        }
      }
      operator delete(v4);
    }
  }
}

```

## disassembly

```asm
0x180011d44  push    rbp
0x180011d46  push    rbx
0x180011d47  push    rsi
0x180011d48  push    rdi
0x180011d49  push    r14
0x180011d4b  push    r15
0x180011d4d  mov     rbp, rsp
0x180011d50  sub     rsp, 48h
0x180011d54  lea     r8, [rbp+dwHandle]; lpdwHandle
0x180011d58  mov     [rbp+dwHandle], 0
0x180011d5f  lea     rdx, wstrFilename; "schedsvc.dll"
0x180011d66  mov     ecx, 1; dwFlags
0x180011d6b  call    cs:__imp_GetFileVersionInfoSizeExW
0x180011d71  mov     edi, eax
0x180011d73  test    eax, eax
0x180011d75  jz      loc_180011F2B
0x180011d7b  mov     ecx, edi; unsigned __int64
0x180011d7d  mov     r15d, edi
0x180011d80  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011d85  mov     rbx, rax
0x180011d88  test    rax, rax
0x180011d8b  jz      loc_180011F2B
0x180011d91  mov     r8d, [rbp+dwHandle]; dwHandle
0x180011d95  lea     rdx, wstrFilename; "schedsvc.dll"
0x180011d9c  mov     r9d, edi; dwLen
0x180011d9f  mov     [rsp+48h+lpData], rax; lpData
0x180011da4  mov     ecx, 3; dwFlags
0x180011da9  call    cs:__imp_GetFileVersionInfoExW
0x180011daf  test    eax, eax
0x180011db1  jz      loc_180011F23
0x180011db7  lea     r9, [rbp+puLen]; puLen
0x180011dbb  mov     [rbp+lpBuffer], 0
0x180011dc3  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x180011dc7  mov     [rbp+puLen], 0
0x180011dce  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x180011dd5  mov     rcx, rbx; pBlock
0x180011dd8  call    cs:__imp_VerQueryValueW
0x180011dde  test    eax, eax
0x180011de0  jz      loc_180011F23
0x180011de6  mov     eax, 2
0x180011deb  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180011df2  mul     r15
0x180011df5  cmovb   rax, rsi
0x180011df9  mov     rcx, rax; unsigned __int64
0x180011dfc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011e01  mov     [rbp+arg_18], 0
0x180011e09  mov     r14, rax
0x180011e0c  mov     [rbp+arg_0], 0
0x180011e13  test    rax, rax
0x180011e16  jz      loc_180011F23
0x180011e1c  xor     edi, edi
0x180011e1e  test    [rbp+puLen], 0FFFFFFFCh
0x180011e25  jbe     loc_180011F1B
0x180011e2b  mov     rcx, [rbp+lpBuffer]
0x180011e2f  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\FileVersion"
0x180011e36  mov     rdx, r15; unsigned __int64
0x180011e39  movzx   eax, word ptr [rcx+rdi*4+2]
0x180011e3e  movzx   r9d, word ptr [rcx+rdi*4]
0x180011e43  mov     rcx, r14; unsigned __int16 *
0x180011e46  mov     dword ptr [rsp+48h+lpData], eax
0x180011e4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011e4f  lea     r9, [rbp+arg_0]; puLen
0x180011e53  mov     rdx, r14; lpSubBlock
0x180011e56  lea     r8, [rbp+arg_18]; lplpBuffer
0x180011e5a  mov     rcx, rbx; pBlock
0x180011e5d  call    cs:__imp_VerQueryValueW
0x180011e63  test    eax, eax
0x180011e65  jz      loc_180011F0B
0x180011e6b  mov     eax, [rbp+arg_0]
0x180011e6e  test    eax, eax
0x180011e70  jz      loc_180011F0B
0x180011e76  cmp     eax, 100h
0x180011e7b  jb      short loc_180011E82
0x180011e7d  mov     eax, 100h
0x180011e82  add     eax, 2
0x180011e85  mov     ecx, eax
0x180011e87  mov     [rbp+arg_0], eax
0x180011e8a  mov     eax, 2
0x180011e8f  mul     rcx
0x180011e92  cmovb   rax, rsi
0x180011e96  mov     rcx, rax; unsigned __int64
0x180011e99  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011e9e  mov     rsi, rax
0x180011ea1  test    rax, rax
0x180011ea4  jz      short loc_180011F07
0x180011ea6  mov     edx, [rbp+arg_0]; unsigned __int64
0x180011ea9  lea     r8, aS; "%s\r\n"
0x180011eb0  mov     r9, [rbp+arg_18]
0x180011eb4  mov     rcx, rax; unsigned __int16 *
0x180011eb7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011ebc  mov     edx, [rbp+arg_0]; unsigned int
0x180011ebf  mov     rcx, rsi; unsigned __int16 *
0x180011ec2  call    ?LogServiceMessage@@YAXPEBGK@Z; LogServiceMessage(ushort const *,ulong)
0x180011ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ece  lea     rax, WPP_GLOBAL_Control
0x180011ed5  cmp     rcx, rax
0x180011ed8  jz      short loc_180011EFF
0x180011eda  test    byte ptr [rcx+1Ch], 2
0x180011ede  jz      short loc_180011EFF
0x180011ee0  cmp     byte ptr [rcx+19h], 4
0x180011ee4  jb      short loc_180011EFF
0x180011ee6  mov     r9, [rbp+arg_18]
0x180011eea  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180011ef1  mov     rcx, [rcx+10h]
0x180011ef5  mov     edx, 29h ; ')'
0x180011efa  call    WPP_SF_S
0x180011eff  mov     rcx, rsi; Block
0x180011f02  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f07  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011f0b  mov     eax, [rbp+puLen]
0x180011f0e  inc     edi
0x180011f10  shr     eax, 2
0x180011f13  cmp     edi, eax
0x180011f15  jb      loc_180011E2B
0x180011f1b  mov     rcx, r14; Block
0x180011f1e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f23  mov     rcx, rbx; Block
0x180011f26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f2b  add     rsp, 48h
0x180011f2f  pop     r15
0x180011f31  pop     r14
0x180011f33  pop     rdi
0x180011f34  pop     rsi
0x180011f35  pop     rbx
0x180011f36  pop     rbp
0x180011f37  retn
```
