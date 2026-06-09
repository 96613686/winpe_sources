# BlbRemoveVolumeMountPoints(ushort *)

- ea: `0x14010164c`
- end: `0x140101868`
- name: `?BlbRemoveVolumeMountPoints@@YAJPEAG@Z`
- size: `540`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, service_task`

## callers

- `0x14004b8b0`

## callees

- `0x14000bb24`
- `0x14000cbcc`
- `0x140014200`
- `0x140014260`
- `0x14010164c`

## import_xrefs

- `KERNEL32!DeleteVolumeMountPointW` at `0x1401017af`
- `KERNEL32!DeleteVolumeMountPointW` at `0x1401017af`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x140101675`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1401016da`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x140101675`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1401016da`
- `KERNEL32!GetLastError` at `0x140101686`
- `KERNEL32!GetLastError` at `0x1401016e8`
- `KERNEL32!GetLastError` at `0x1401017d0`
- `KERNEL32!GetLastError` at `0x140101686`
- `KERNEL32!GetLastError` at `0x1401016e8`
- `KERNEL32!GetLastError` at `0x1401017d0`
- `ole32!CoTaskMemFree` at `0x140101828`
- `ole32!CoTaskMemFree` at `0x140101828`

## pseudocode

```c
__int64 __fastcall BlbRemoveVolumeMountPoints(LPCWSTR lpszVolumeName)
{
  unsigned int v1; // ebx
  WCHAR *v2; // rsi
  const WCHAR *i; // rdi
  signed int v4; // eax
  int v5; // eax
  signed int v6; // eax
  PVOID *v7; // rcx
  int v8; // edx
  __int64 v9; // rax
  signed int LastError; // eax
  DWORD cchBufferLength; // [rsp+68h] [rbp+10h] BYREF
  DWORD cchReturnLength; // [rsp+70h] [rbp+18h] BYREF
  void *v14; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  cchBufferLength = 0;
  v1 = 0;
  cchReturnLength = 0;
  v2 = 0;
  i = lpszVolumeName;
  if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, 0, 0, &cchBufferLength) )
  {
LABEL_6:
    if ( GetVolumePathNamesForVolumeNameW(i, v2, cchBufferLength, &cchReturnLength) )
    {
      for ( i = v2; *i; i += v9 + 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids, i);
        }
        if ( !DeleteVolumeMountPointW(i) )
        {
          LastError = GetLastError();
          v1 = LastError;
          if ( LastError > 0 )
            v1 = (unsigned __int16)LastError | 0x80070000;
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 59;
            goto LABEL_33;
          }
          goto LABEL_35;
        }
        v9 = -1;
        do
          ++v9;
        while ( i[v9] );
      }
    }
    else
    {
      v6 = GetLastError();
      v1 = v6;
      if ( v6 > 0 )
        v1 = (unsigned __int16)v6 | 0x80070000;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_35:
        if ( v2 )
        {
          CoTaskMemFree(v2);
          goto LABEL_37;
        }
        goto LABEL_38;
      }
      v8 = 57;
LABEL_33:
      WPP_SF_Sd((unsigned int)v7[2], v8, (unsigned int)WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids, (_DWORD)i, v1);
    }
LABEL_34:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  v4 = GetLastError();
  v1 = v4;
  if ( v4 > 0 )
    v1 = (unsigned __int16)v4 | 0x80070000;
  if ( v1 == -2147024662 )
  {
    v5 = BlbutilMemalloc(&v14, cchBufferLength, 2u);
    v2 = (WCHAR *)v14;
    v1 = v5;
    if ( v5 < 0 )
      goto LABEL_34;
    goto LABEL_6;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      (unsigned int)WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids,
      (_DWORD)i,
      v1);
LABEL_37:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_38:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
    WPP_SF_(v7[2], 60, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
  return v1;
}

```

## disassembly

```asm
0x14010164c  mov     rax, rsp
0x14010164f  push    rbx
0x140101650  push    rbp
0x140101651  push    rsi
0x140101652  push    rdi
0x140101653  push    r15
0x140101655  sub     rsp, 30h
0x140101659  xor     ebp, ebp
0x14010165b  lea     r9, [rax+10h]; lpcchReturnLength
0x14010165f  xor     r8d, r8d; cchBufferLength
0x140101662  mov     [rax+20h], rbp
0x140101666  xor     edx, edx; lpszVolumePathNames
0x140101668  mov     [rax+10h], ebp
0x14010166b  mov     ebx, ebp
0x14010166d  mov     [rax+18h], ebp
0x140101670  mov     esi, ebp
0x140101672  mov     rdi, rcx
0x140101675  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14010167b  lea     r15, WPP_GLOBAL_Control
0x140101682  test    eax, eax
0x140101684  jnz     short loc_1401016CA
0x140101686  call    cs:__imp_GetLastError
0x14010168c  mov     ebx, eax
0x14010168e  test    eax, eax
0x140101690  jle     short loc_14010169B
0x140101692  movzx   ebx, ax
0x140101695  or      ebx, 80070000h
0x14010169b  cmp     ebx, 800700EAh
0x1401016a1  jnz     loc_14010172B
0x1401016a7  mov     edx, [rsp+58h+cchBufferLength]; unsigned int
0x1401016ab  lea     rcx, [rsp+58h+arg_18]; void **
0x1401016b0  mov     r8d, 2; unsigned int
0x1401016b6  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1401016bb  mov     rsi, [rsp+58h+arg_18]
0x1401016c0  mov     ebx, eax
0x1401016c2  test    eax, eax
0x1401016c4  js      loc_140101819
0x1401016ca  mov     r8d, [rsp+58h+cchBufferLength]; cchBufferLength
0x1401016cf  lea     r9, [rsp+58h+cchReturnLength]; lpcchReturnLength
0x1401016d4  mov     rdx, rsi; lpszVolumePathNames
0x1401016d7  mov     rcx, rdi; lpszVolumeName
0x1401016da  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1401016e0  test    eax, eax
0x1401016e2  jnz     loc_140101770
0x1401016e8  call    cs:__imp_GetLastError
0x1401016ee  mov     ebx, eax
0x1401016f0  test    eax, eax
0x1401016f2  jle     short loc_1401016FD
0x1401016f4  movzx   ebx, ax
0x1401016f7  or      ebx, 80070000h
0x1401016fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140101704  cmp     rcx, r15
0x140101707  jz      loc_140101820
0x14010170d  test    byte ptr [rcx+1Ch], 1
0x140101711  jz      loc_140101820
0x140101717  cmp     byte ptr [rcx+19h], 2
0x14010171b  jb      loc_140101820
0x140101721  mov     edx, 39h ; '9'
0x140101726  jmp     loc_140101802
0x14010172b  mov     rcx, cs:WPP_GLOBAL_Control
0x140101732  cmp     rcx, r15
0x140101735  jz      loc_14010185B
0x14010173b  test    byte ptr [rcx+1Ch], 1
0x14010173f  jz      loc_140101835
0x140101745  cmp     byte ptr [rcx+19h], 2
0x140101749  jb      loc_140101835
0x14010174f  mov     rcx, [rcx+10h]
0x140101753  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x14010175a  mov     edx, 38h ; '8'
0x14010175f  mov     [rsp+58h+var_38], ebx
0x140101763  mov     r9, rdi
0x140101766  call    WPP_SF_Sd
0x14010176b  jmp     loc_14010182E
0x140101770  mov     rdi, rsi
0x140101773  cmp     [rdi], bp
0x140101776  jz      loc_140101819
0x14010177c  mov     rcx, cs:WPP_GLOBAL_Control
0x140101783  cmp     rcx, r15
0x140101786  jz      short loc_1401017AC
0x140101788  test    byte ptr [rcx+1Ch], 1
0x14010178c  jz      short loc_1401017AC
0x14010178e  cmp     byte ptr [rcx+19h], 4
0x140101792  jb      short loc_1401017AC
0x140101794  mov     rcx, [rcx+10h]
0x140101798  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x14010179f  mov     edx, 3Ah ; ':'
0x1401017a4  mov     r9, rdi
0x1401017a7  call    WPP_SF_S
0x1401017ac  mov     rcx, rdi; lpszVolumeMountPoint
0x1401017af  call    cs:__imp_DeleteVolumeMountPointW
0x1401017b5  test    eax, eax
0x1401017b7  jz      short loc_1401017D0
0x1401017b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1401017bd  inc     rax
0x1401017c0  cmp     [rdi+rax*2], bp
0x1401017c4  jnz     short loc_1401017BD
0x1401017c6  lea     rdi, [rdi+rax*2]
0x1401017ca  add     rdi, 2
0x1401017ce  jmp     short loc_140101773
0x1401017d0  call    cs:__imp_GetLastError
0x1401017d6  mov     ebx, eax
0x1401017d8  test    eax, eax
0x1401017da  jle     short loc_1401017E5
0x1401017dc  movzx   ebx, ax
0x1401017df  or      ebx, 80070000h
0x1401017e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1401017ec  cmp     rcx, r15
0x1401017ef  jz      short loc_140101820
0x1401017f1  test    byte ptr [rcx+1Ch], 1
0x1401017f5  jz      short loc_140101820
0x1401017f7  cmp     byte ptr [rcx+19h], 2
0x1401017fb  jb      short loc_140101820
0x1401017fd  mov     edx, 3Bh ; ';'
0x140101802  mov     rcx, [rcx+10h]
0x140101806  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x14010180d  mov     r9, rdi
0x140101810  mov     [rsp+58h+var_38], ebx
0x140101814  call    WPP_SF_Sd
0x140101819  mov     rcx, cs:WPP_GLOBAL_Control
0x140101820  test    rsi, rsi
0x140101823  jz      short loc_140101835
0x140101825  mov     rcx, rsi; pv
0x140101828  call    cs:__imp_CoTaskMemFree
0x14010182e  mov     rcx, cs:WPP_GLOBAL_Control
0x140101835  cmp     rcx, r15
0x140101838  jz      short loc_14010185B
0x14010183a  test    byte ptr [rcx+1Ch], 1
0x14010183e  jz      short loc_14010185B
0x140101840  cmp     byte ptr [rcx+19h], 4
0x140101844  jb      short loc_14010185B
0x140101846  mov     rcx, [rcx+10h]
0x14010184a  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x140101851  mov     edx, 3Ch ; '<'
0x140101856  call    WPP_SF_
0x14010185b  mov     eax, ebx
0x14010185d  add     rsp, 30h
0x140101861  pop     r15
0x140101863  pop     rdi
0x140101864  pop     rsi
0x140101865  pop     rbp
0x140101866  pop     rbx
0x140101867  retn
```
