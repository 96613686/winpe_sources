# RecordFileVersion(void)

- ea: `0x180012858`
- end: `0x180012a65`
- name: `?RecordFileVersion@@YAXXZ`
- size: `525`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180011958`

## callees

- `0x180006314`
- `0x180007988`
- `0x180007994`
- `0x18000d128`
- `0x180012858`
- `0x18002e304`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800128f8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180012983`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800128f8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180012983`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800128c3`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800128c3`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18001287f`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18001287f`

## string_xrefs

- `0x180012873`: `schedsvc.dll`
- `0x1800128af`: `schedsvc.dll`

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
0x180012858  push    rbp
0x18001285a  push    rbx
0x18001285b  push    rsi
0x18001285c  push    rdi
0x18001285d  push    r14
0x18001285f  push    r15
0x180012861  mov     rbp, rsp
0x180012864  sub     rsp, 48h
0x180012868  lea     r8, [rbp+dwHandle]; lpdwHandle
0x18001286c  mov     [rbp+dwHandle], 0
0x180012873  lea     rdx, wstrFilename; "schedsvc.dll"
0x18001287a  mov     ecx, 1; dwFlags
0x18001287f  call    cs:__imp_GetFileVersionInfoSizeExW
0x180012886  nop     dword ptr [rax+rax+00h]
0x18001288b  mov     edi, eax
0x18001288d  test    eax, eax
0x18001288f  jz      loc_180012A57
0x180012895  mov     ecx, edi; unsigned __int64
0x180012897  mov     r15d, edi
0x18001289a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001289f  mov     rbx, rax
0x1800128a2  test    rax, rax
0x1800128a5  jz      loc_180012A57
0x1800128ab  mov     r8d, [rbp+dwHandle]; dwHandle
0x1800128af  lea     rdx, wstrFilename; "schedsvc.dll"
0x1800128b6  mov     r9d, edi; dwLen
0x1800128b9  mov     [rsp+48h+lpData], rax; lpData
0x1800128be  mov     ecx, 3; dwFlags
0x1800128c3  call    cs:__imp_GetFileVersionInfoExW
0x1800128ca  nop     dword ptr [rax+rax+00h]
0x1800128cf  test    eax, eax
0x1800128d1  jz      loc_180012A4F
0x1800128d7  lea     r9, [rbp+puLen]; puLen
0x1800128db  mov     [rbp+lpBuffer], 0
0x1800128e3  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x1800128e7  mov     [rbp+puLen], 0
0x1800128ee  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x1800128f5  mov     rcx, rbx; pBlock
0x1800128f8  call    cs:__imp_VerQueryValueW
0x1800128ff  nop     dword ptr [rax+rax+00h]
0x180012904  test    eax, eax
0x180012906  jz      loc_180012A4F
0x18001290c  mov     eax, 2
0x180012911  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180012918  mul     r15
0x18001291b  cmovb   rax, rsi
0x18001291f  mov     rcx, rax; unsigned __int64
0x180012922  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012927  mov     [rbp+arg_18], 0
0x18001292f  mov     r14, rax
0x180012932  mov     [rbp+arg_0], 0
0x180012939  test    rax, rax
0x18001293c  jz      loc_180012A4F
0x180012942  xor     edi, edi
0x180012944  test    [rbp+puLen], 0FFFFFFFCh
0x18001294b  jbe     loc_180012A47
0x180012951  mov     rcx, [rbp+lpBuffer]
0x180012955  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\FileVersion"
0x18001295c  mov     rdx, r15; unsigned __int64
0x18001295f  movzx   eax, word ptr [rcx+rdi*4+2]
0x180012964  movzx   r9d, word ptr [rcx+rdi*4]
0x180012969  mov     rcx, r14; unsigned __int16 *
0x18001296c  mov     dword ptr [rsp+48h+lpData], eax
0x180012970  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012975  lea     r9, [rbp+arg_0]; puLen
0x180012979  mov     rdx, r14; lpSubBlock
0x18001297c  lea     r8, [rbp+arg_18]; lplpBuffer
0x180012980  mov     rcx, rbx; pBlock
0x180012983  call    cs:__imp_VerQueryValueW
0x18001298a  nop     dword ptr [rax+rax+00h]
0x18001298f  test    eax, eax
0x180012991  jz      loc_180012A37
0x180012997  mov     eax, [rbp+arg_0]
0x18001299a  test    eax, eax
0x18001299c  jz      loc_180012A37
0x1800129a2  cmp     eax, 100h
0x1800129a7  jb      short loc_1800129AE
0x1800129a9  mov     eax, 100h
0x1800129ae  add     eax, 2
0x1800129b1  mov     ecx, eax
0x1800129b3  mov     [rbp+arg_0], eax
0x1800129b6  mov     eax, 2
0x1800129bb  mul     rcx
0x1800129be  cmovb   rax, rsi
0x1800129c2  mov     rcx, rax; unsigned __int64
0x1800129c5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800129ca  mov     rsi, rax
0x1800129cd  test    rax, rax
0x1800129d0  jz      short loc_180012A33
0x1800129d2  mov     edx, [rbp+arg_0]; unsigned __int64
0x1800129d5  lea     r8, aS; "%s\r\n"
0x1800129dc  mov     r9, [rbp+arg_18]
0x1800129e0  mov     rcx, rax; unsigned __int16 *
0x1800129e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800129e8  mov     edx, [rbp+arg_0]; unsigned int
0x1800129eb  mov     rcx, rsi; unsigned __int16 *
0x1800129ee  call    ?LogServiceMessage@@YAXPEBGK@Z; LogServiceMessage(ushort const *,ulong)
0x1800129f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129fa  lea     rax, WPP_GLOBAL_Control
0x180012a01  cmp     rcx, rax
0x180012a04  jz      short loc_180012A2B
0x180012a06  test    byte ptr [rcx+1Ch], 2
0x180012a0a  jz      short loc_180012A2B
0x180012a0c  cmp     byte ptr [rcx+19h], 4
0x180012a10  jb      short loc_180012A2B
0x180012a12  mov     r9, [rbp+arg_18]
0x180012a16  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180012a1d  mov     rcx, [rcx+10h]
0x180012a21  mov     edx, 29h ; ')'
0x180012a26  call    WPP_SF_S
0x180012a2b  mov     rcx, rsi; Block
0x180012a2e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012a33  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012a37  mov     eax, [rbp+puLen]
0x180012a3a  inc     edi
0x180012a3c  shr     eax, 2
0x180012a3f  cmp     edi, eax
0x180012a41  jb      loc_180012951
0x180012a47  mov     rcx, r14; Block
0x180012a4a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012a4f  mov     rcx, rbx; Block
0x180012a52  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012a57  add     rsp, 48h
0x180012a5b  pop     r15
0x180012a5d  pop     r14
0x180012a5f  pop     rdi
0x180012a60  pop     rsi
0x180012a61  pop     rbx
0x180012a62  pop     rbp
0x180012a63  retn
```
