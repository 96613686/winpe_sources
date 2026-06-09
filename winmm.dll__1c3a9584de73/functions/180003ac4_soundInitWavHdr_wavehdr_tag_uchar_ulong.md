# soundInitWavHdr(wavehdr_tag *,uchar *,ulong)

- ea: `0x180003ac4`
- end: `0x180003e85`
- name: `?soundInitWavHdr@@YAHPEAUwavehdr_tag@@PEAEK@Z`
- size: `961`
- prototype: `__int64 __fastcall(struct wavehdr_tag *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180002ca0`
- `0x18000b260`

## callees

- `0x180003ac4`
- `0x18000b6d4`
- `0x18001a811`
- `0x18001a81d`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c9b`
- `api-ms-win-core-kernel32-private-l1-1-2!CheckForReadOnlyResource` at `0x18001a985`
- `api-ms-win-core-kernel32-private-l1-1-2!CheckForReadOnlyResource` at `0x18001a985`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180003c2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180003c2e`

## pseudocode

```c
__int64 __fastcall soundInitWavHdr(struct wavehdr_tag *a1, unsigned __int8 *a2, unsigned int a3)
{
  unsigned int v5; // r9d
  unsigned __int8 *i; // r8
  __int64 v7; // rax
  unsigned __int64 v8; // rdx
  _WORD *v9; // rbx
  unsigned int v10; // r15d
  unsigned int v11; // ecx
  unsigned __int8 *j; // rdi
  __int64 v13; // rax
  DWORD *v14; // r14
  unsigned __int64 v15; // rdx
  DWORD v16; // r12d
  CHAR *v17; // rdi
  DWORD v18; // r14d
  unsigned int v19; // eax
  HLOCAL v20; // rax
  DWORD_PTR v21; // r14
  int v23; // ecx
  int v24; // edi
  __int64 v25; // rax
  __int64 v26; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-68h] BYREF
  CHAR *v29; // [rsp+B8h] [rbp+20h]

  v5 = 12;
  if ( a3 < 0xC )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids);
    }
  }
  else if ( *(_DWORD *)a2 == 1179011410 && *((_DWORD *)a2 + 2) == 1163280727 && a3 >= *((_DWORD *)a2 + 1) )
  {
    for ( i = a2 + 12; ; i += v8 + 8 )
    {
      v7 = a3 - v5;
      if ( (unsigned int)v7 < 8 )
        break;
      v8 = *((unsigned int *)i + 1);
      if ( v8 > v7 - 8 )
        break;
      if ( *(_DWORD *)i == 544501094 )
      {
        if ( (unsigned int)v8 < 0xE )
          return 0;
        v9 = i + 8;
        v10 = *((_DWORD *)i + 1);
        if ( (unsigned int)v8 >= 0x12 )
        {
          if ( *((_WORD *)i + 12) >= 0x400u )
            return 0;
          if ( *((unsigned __int16 *)i + 12) + 18LL != v8 )
            return 0;
          if ( ((*v9 - 1) & 0xFFFD) == 0 )
          {
            if ( *((_WORD *)i + 12) )
              return 0;
            v23 = *((unsigned __int16 *)i + 11);
            if ( (v23 & 7) != 0
              || *((_WORD *)i + 5) > 2u
              || *((_DWORD *)i + 4) != (v23 * *((_DWORD *)i + 3) * (unsigned int)*((unsigned __int16 *)i + 5)) >> 3 )
            {
              return 0;
            }
          }
        }
        else if ( (unsigned int)v8 >= 0x10 )
        {
          v10 = 16;
        }
        if ( *((_WORD *)i + 5) && *((_DWORD *)i + 3) && *((_DWORD *)i + 4) && *((_WORD *)i + 10) )
        {
          if ( *v9 != 0xFFFE )
            goto LABEL_18;
          if ( v10 >= 0x28 )
          {
            if ( *((_WORD *)i + 13) )
            {
              v24 = *((unsigned __int16 *)i + 11);
              if ( (unsigned __int16)v24 >= *((_WORD *)i + 13) )
              {
                v25 = *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 - *((_QWORD *)i + 4);
                if ( *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 == *((_QWORD *)i + 4) )
                  v25 = *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4 - *((_QWORD *)i + 5);
                if ( v25 )
                {
                  v26 = *(_QWORD *)&GUID_00000003_0000_0010_8000_00aa00389b71.Data1 - *((_QWORD *)i + 4);
                  if ( *(_QWORD *)&GUID_00000003_0000_0010_8000_00aa00389b71.Data1 == *((_QWORD *)i + 4) )
                    v26 = *(_QWORD *)GUID_00000003_0000_0010_8000_00aa00389b71.Data4 - *((_QWORD *)i + 5);
                  if ( v26 )
                    goto LABEL_18;
                }
                if ( *((_DWORD *)i + 4) == (*((_DWORD *)i + 3) * v24 * (unsigned int)*((unsigned __int16 *)i + 5)) >> 3 )
                {
LABEL_18:
                  v11 = v5 + v8 + 8;
                  for ( j = &i[v8 + 8]; ; j += v15 + 8 )
                  {
                    v13 = a3 - v11;
                    if ( (unsigned int)v13 < 8 )
                      break;
                    v14 = (DWORD *)(j + 4);
                    v15 = *((unsigned int *)j + 1);
                    if ( v15 > v13 - 8 )
                      break;
                    if ( *(_DWORD *)j == 1635017060 )
                    {
                      if ( (((_BYTE)v9 - (_BYTE)a2) & 3) != 0 )
                      {
                        v9 = (_WORD *)((char *)v9 - (((_BYTE)v9 - (_BYTE)a2) & 3));
                        memmove_0(v9, i + 8, v10);
                      }
                      v17 = (CHAR *)(j + 8);
                      v18 = *v14;
                      v16 = v18;
                      v29 = v17;
                      memset(&SystemInfo, 0, sizeof(SystemInfo));
                      GetSystemInfo(&SystemInfo);
                      for ( ; v18 > SystemInfo.dwPageSize; v18 -= SystemInfo.dwPageSize )
                        v29 += SystemInfo.dwPageSize;
                      v19 = 18;
                      if ( v10 > 0x12 )
                        v19 = v10;
                      v20 = LocalAlloc(0x40u, v19);
                      v21 = (DWORD_PTR)v20;
                      if ( v20 )
                      {
                        memcpy_0(v20, v9, v10);
                        a1->lpData = v17;
                        a1->dwBufferLength = v16;
                        a1->dwUser = v21;
                        *(_QWORD *)&a1->dwFlags = 1;
                        return 1;
                      }
                      return 0;
                    }
                    v11 += v15 + 8;
                    if ( v11 >= *((_DWORD *)a2 + 1) )
                      return 0;
                  }
                }
              }
            }
          }
        }
        return 0;
      }
      v5 += v8 + 8;
      if ( v5 >= *((_DWORD *)a2 + 1) )
        return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003ac4  mov     [rsp+arg_0], rcx
0x180003ac9  push    rbx
0x180003aca  push    rsi
0x180003acb  push    rdi
0x180003acc  push    r12
0x180003ace  push    r13
0x180003ad0  push    r14
0x180003ad2  push    r15
0x180003ad4  sub     rsp, 60h
0x180003ad8  mov     r11d, r8d
0x180003adb  mov     r10, rdx
0x180003ade  mov     r9d, 0Ch
0x180003ae4  cmp     r8d, r9d
0x180003ae7  jb      loc_180003D1C
0x180003aed  cmp     dword ptr [rdx], 46464952h
0x180003af3  jnz     loc_180003CAD
0x180003af9  cmp     dword ptr [rdx+8], 45564157h
0x180003b00  jnz     loc_180003CAD
0x180003b06  cmp     r8d, [rdx+4]
0x180003b0a  jb      loc_180003CAD
0x180003b10  lea     r8, [rdx+0Ch]
0x180003b14  mov     eax, r11d
0x180003b17  sub     eax, r9d
0x180003b1a  cmp     eax, 8
0x180003b1d  jb      loc_180003CAD
0x180003b23  mov     edx, [r8+4]
0x180003b27  sub     rax, 8
0x180003b2b  cmp     rdx, rax
0x180003b2e  ja      loc_180003CAD
0x180003b34  cmp     dword ptr [r8], 20746D66h
0x180003b3b  jnz     loc_180003E68
0x180003b41  cmp     edx, 0Eh
0x180003b44  jb      loc_180003CAD
0x180003b4a  lea     rbx, [r8+8]
0x180003b4e  mov     r15d, edx
0x180003b51  mov     [rsp+98h+arg_10], edx
0x180003b58  mov     r13d, 12h
0x180003b5e  cmp     edx, r13d
0x180003b61  jnb     loc_180003CBF
0x180003b67  lea     eax, [r13-2]
0x180003b6b  cmp     edx, eax
0x180003b6d  cmovnb  r15d, eax
0x180003b71  mov     [rsp+98h+arg_10], r15d
0x180003b79  xor     esi, esi
0x180003b7b  cmp     si, [rbx+2]
0x180003b7f  jz      loc_180003CAD
0x180003b85  cmp     [rbx+4], esi
0x180003b88  jz      loc_180003CAD
0x180003b8e  cmp     [rbx+8], esi
0x180003b91  jz      loc_180003CAD
0x180003b97  cmp     si, [rbx+0Ch]
0x180003b9b  jz      loc_180003CAD
0x180003ba1  mov     eax, 0FFFEh
0x180003ba6  cmp     ax, [rbx]
0x180003ba9  jz      loc_180003D64
0x180003baf  lea     ecx, [rdx+8]
0x180003bb2  add     ecx, r9d
0x180003bb5  lea     rdi, [rdx+8]
0x180003bb9  add     rdi, r8
0x180003bbc  mov     [rsp+98h+arg_18], rdi
0x180003bc4  mov     eax, r11d
0x180003bc7  sub     eax, ecx
0x180003bc9  cmp     eax, 8
0x180003bcc  jb      loc_180003CAD
0x180003bd2  lea     r14, [rdi+4]
0x180003bd6  mov     [rsp+98h+var_70], r14
0x180003bdb  mov     edx, [r14]
0x180003bde  sub     rax, 8
0x180003be2  cmp     rdx, rax
0x180003be5  ja      loc_180003CAD
0x180003beb  cmp     dword ptr [rdi], 61746164h
0x180003bf1  jnz     loc_180003E4D
0x180003bf7  mov     eax, ebx
0x180003bf9  sub     eax, r10d
0x180003bfc  and     eax, 3
0x180003bff  jnz     loc_180003DE0
0x180003c05  mov     r12d, [r14]
0x180003c08  add     rdi, 8
0x180003c0c  mov     r14d, r12d
0x180003c0f  mov     [rsp+98h+arg_18], rdi
0x180003c17  xorps   xmm0, xmm0
0x180003c1a  movups  xmmword ptr [rsp+98h+SystemInfo], xmm0
0x180003c1f  movups  xmmword ptr [rsp+98h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180003c24  movups  xmmword ptr [rsp+98h+SystemInfo.dwNumberOfProcessors], xmm0
0x180003c29  lea     rcx, [rsp+98h+SystemInfo]; lpSystemInfo
0x180003c2e  call    cs:__imp_GetSystemInfo
0x180003c34  cmp     r12d, [rsp+98h+SystemInfo.dwPageSize]
0x180003c39  jbe     short loc_180003C6F
0x180003c3b  mov     rax, [rsp+98h+arg_18]
0x180003c43  mov     cl, [rax]
0x180003c45  mov     byte ptr [rsp+98h+arg_10], cl
0x180003c4c  mov     eax, [rsp+98h+SystemInfo.dwPageSize]
0x180003c50  mov     rcx, [rsp+98h+arg_18]
0x180003c58  add     rcx, rax
0x180003c5b  mov     [rsp+98h+arg_18], rcx
0x180003c63  sub     r14d, [rsp+98h+SystemInfo.dwPageSize]
0x180003c68  cmp     r14d, [rsp+98h+SystemInfo.dwPageSize]
0x180003c6d  ja      short loc_180003C3B
0x180003c6f  test    r14d, r14d
0x180003c72  jz      short loc_180003C85
0x180003c74  mov     rax, [rsp+98h+arg_18]
0x180003c7c  mov     cl, [rax]
0x180003c7e  mov     byte ptr [rsp+98h+arg_10], cl
0x180003c85  mov     r13d, r15d
0x180003c88  mov     eax, 12h
0x180003c8d  cmp     r15d, eax
0x180003c90  cmova   eax, r13d
0x180003c94  mov     edx, eax; uBytes
0x180003c96  mov     ecx, 40h ; '@'; uFlags
0x180003c9b  call    cs:__imp_LocalAlloc
0x180003ca1  mov     r14, rax
0x180003ca4  test    rax, rax
0x180003ca7  jnz     loc_180003E1A
0x180003cad  xor     eax, eax
0x180003caf  add     rsp, 60h
0x180003cb3  pop     r15
0x180003cb5  pop     r14
0x180003cb7  pop     r13
0x180003cb9  pop     r12
0x180003cbb  pop     rdi
0x180003cbc  pop     rsi
0x180003cbd  pop     rbx
0x180003cbe  retn
0x180003cbf  mov     eax, 400h
0x180003cc4  cmp     [rbx+10h], ax
0x180003cc8  jnb     short loc_180003CAD
0x180003cca  movzx   eax, word ptr [rbx+10h]
0x180003cce  add     rax, r13
0x180003cd1  cmp     rax, rdx
0x180003cd4  jnz     short loc_180003CAD
0x180003cd6  movzx   eax, word ptr [rbx]
0x180003cd9  dec     ax
0x180003cdc  mov     ecx, 0FFFDh
0x180003ce1  xor     esi, esi
0x180003ce3  test    cx, ax
0x180003ce6  jnz     loc_180003B7B
0x180003cec  cmp     si, [rbx+10h]
0x180003cf0  jnz     short loc_180003CAD
0x180003cf2  movzx   ecx, word ptr [rbx+0Eh]
0x180003cf6  test    cl, 7
0x180003cf9  jnz     short loc_180003CAD
0x180003cfb  lea     eax, [rsi+2]
0x180003cfe  cmp     ax, [rbx+2]
0x180003d02  jb      short loc_180003CAD
0x180003d04  movzx   eax, word ptr [rbx+2]
0x180003d08  imul    eax, [rbx+4]
0x180003d0c  imul    eax, ecx
0x180003d0f  shr     eax, 3
0x180003d12  cmp     [rbx+8], eax
0x180003d15  jnz     short loc_180003CAD
0x180003d17  jmp     loc_180003B7B
0x180003d1c  lea     rax, WPP_GLOBAL_Control
0x180003d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d2a  cmp     rcx, rax
0x180003d2d  jz      loc_180003CAD
0x180003d33  test    dword ptr [rcx+1Ch], 400000h
0x180003d3a  jz      loc_180003CAD
0x180003d40  cmp     byte ptr [rcx+19h], 3
0x180003d44  jb      loc_180003CAD
0x180003d4a  mov     edx, 1Dh
0x180003d4f  lea     r8, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids
0x180003d56  mov     rcx, [rcx+10h]
0x180003d5a  call    WPP_SF_
0x180003d5f  jmp     loc_180003CAD
0x180003d64  cmp     r15d, 28h ; '('
0x180003d68  jb      loc_180003CAD
0x180003d6e  cmp     si, [rbx+12h]
0x180003d72  jz      loc_180003CAD
0x180003d78  movzx   edi, word ptr [rbx+0Eh]
0x180003d7c  cmp     di, [rbx+12h]
0x180003d80  jb      loc_180003CAD
0x180003d86  mov     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data1
0x180003d8d  sub     rax, [rbx+18h]
0x180003d91  jnz     short loc_180003D9E
0x180003d93  mov     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data4
0x180003d9a  sub     rax, [rbx+20h]
0x180003d9e  test    rax, rax
0x180003da1  jz      short loc_180003DC4
0x180003da3  mov     rax, qword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data1
0x180003daa  sub     rax, [rbx+18h]
0x180003dae  jnz     short loc_180003DBB
0x180003db0  mov     rax, qword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data4
0x180003db7  sub     rax, [rbx+20h]
0x180003dbb  test    rax, rax
0x180003dbe  jnz     loc_180003BAF
0x180003dc4  movzx   ecx, word ptr [rbx+2]
0x180003dc8  imul    ecx, edi
0x180003dcb  imul    ecx, [rbx+4]
0x180003dcf  shr     ecx, 3
0x180003dd2  cmp     [rbx+8], ecx
0x180003dd5  jnz     loc_180003CAD
0x180003ddb  jmp     loc_180003BAF
0x180003de0  mov     rdx, rbx; Src
0x180003de3  sub     rbx, rax
0x180003de6  mov     [rsp+98h+var_78], rbx
0x180003deb  mov     r8d, r15d; Size
0x180003dee  mov     rcx, rbx; void *
0x180003df1  call    memmove_0
0x180003df6  jmp     loc_180003C05
0x180003dfb  mov     rbx, [rsp+98h+var_78]
0x180003e00  mov     rdi, [rsp+98h+arg_18]
0x180003e08  mov     r15d, [rsp+98h+arg_10]
0x180003e10  mov     r14, [rsp+98h+var_70]
0x180003e15  jmp     loc_180003C05
0x180003e1a  mov     r8, r13; Size
0x180003e1d  mov     rdx, rbx; Src
0x180003e20  mov     rcx, r14; void *
0x180003e23  call    memcpy_0
0x180003e28  mov     rax, [rsp+98h+arg_0]
0x180003e30  mov     [rax], rdi
0x180003e33  mov     [rax+8], r12d
0x180003e37  mov     [rax+10h], r14
0x180003e3b  mov     qword ptr [rax+18h], 1
0x180003e43  mov     eax, 1
0x180003e48  jmp     loc_180003CAF
0x180003e4d  add     ecx, 8
0x180003e50  add     ecx, edx
0x180003e52  cmp     ecx, [r10+4]
0x180003e56  jnb     loc_180003CAD
0x180003e5c  add     rdi, 8
0x180003e60  add     rdi, rdx
0x180003e63  jmp     loc_180003BBC
0x180003e68  add     r9d, 8
0x180003e6c  add     r9d, edx
0x180003e6f  cmp     r9d, [r10+4]
0x180003e73  jnb     loc_180003CAD
0x180003e79  add     r8, 8
0x180003e7d  add     r8, rdx
0x180003e80  jmp     loc_180003B14
0x18001a97a  push    rbp
0x18001a97c  sub     rsp, 20h
0x18001a980  mov     rbp, rdx
0x18001a983  xor     edx, edx
0x18001a985  call    cs:__imp_CheckForReadOnlyResource
0x18001a98b  nop
0x18001a98c  add     rsp, 20h
0x18001a990  pop     rbp
0x18001a991  retn
```
