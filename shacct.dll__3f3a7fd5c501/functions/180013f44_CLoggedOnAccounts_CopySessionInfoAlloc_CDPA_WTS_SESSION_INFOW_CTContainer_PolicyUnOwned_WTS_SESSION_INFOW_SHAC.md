# CLoggedOnAccounts::_CopySessionInfoAlloc(CDPA<_WTS_SESSION_INFOW,CTContainer_PolicyUnOwned<_WTS_SESSION_INFOW>> *,_SHACCT_LOGON_INFO * *)

- ea: `0x180013f44`
- end: `0x180013ff5`
- name: `?_CopySessionInfoAlloc@CLoggedOnAccounts@@AEAAJPEAV?$CDPA@U_WTS_SESSION_INFOW@@V?$CTContainer_PolicyUnOwned@U_WTS_SESSION_INFOW@@@@@@PEAPEAU_SHACCT_LOGON_INFO@@@Z`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008640`

## callees

- `0x18000b828`
- `0x180013f44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013fe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013fe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013f74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013f74`

## pseudocode

```c
__int64 __fastcall CLoggedOnAccounts::_CopySessionInfoAlloc(__int64 a1, __int64 a2, _QWORD *a3)
{
  _DWORD *v4; // rdi
  int v6; // ebx
  char *v7; // r11
  unsigned int v8; // ebp
  __int64 v9; // r8
  __int64 v10; // rcx
  int v11; // eax

  *a3 = 0;
  v4 = *(_DWORD **)a2;
  v6 = -2147024882;
  if ( *(_QWORD *)a2 )
    LODWORD(v4) = *v4;
  v7 = (char *)CoTaskMemAlloc(528LL * (unsigned int)v4);
  if ( v7 )
  {
    v6 = 0;
    v8 = 0;
    if ( (_DWORD)v4 )
    {
      while ( v6 >= 0 )
      {
        v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 8LL * (int)v8);
        v10 = 528LL * v8;
        *(_DWORD *)&v7[v10] = *(_DWORD *)v9;
        *(_DWORD *)&v7[v10 + 524] = *(_DWORD *)(v9 + 16);
        v11 = StringCchCopyW((unsigned __int16 *)&v7[v10 + 4], 0x104u, *(const unsigned __int16 **)(v9 + 8));
        ++v8;
        v6 = v11;
        if ( v8 >= (unsigned int)v4 )
        {
          if ( v11 < 0 )
            break;
          goto LABEL_8;
        }
      }
    }
    else
    {
LABEL_8:
      *a3 = v7;
      v7 = 0;
    }
    CoTaskMemFree(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013f44  push    rbx
0x180013f46  push    rbp
0x180013f47  push    rsi
0x180013f48  push    rdi
0x180013f49  push    r14
0x180013f4b  sub     rsp, 20h
0x180013f4f  mov     qword ptr [r8], 0
0x180013f56  mov     rsi, r8
0x180013f59  mov     rdi, [rdx]
0x180013f5c  mov     r14, rdx
0x180013f5f  mov     ebx, 8007000Eh
0x180013f64  test    rdi, rdi
0x180013f67  jz      short loc_180013F6B
0x180013f69  mov     edi, [rdi]
0x180013f6b  mov     eax, edi
0x180013f6d  imul    rcx, rax, 210h; cb
0x180013f74  call    cs:__imp_CoTaskMemAlloc
0x180013f7a  mov     r11, rax
0x180013f7d  test    rax, rax
0x180013f80  jz      short loc_180013FE8
0x180013f82  xor     ebx, ebx
0x180013f84  xor     ebp, ebp
0x180013f86  test    edi, edi
0x180013f88  jz      short loc_180013FD9
0x180013f8a  test    ebx, ebx
0x180013f8c  js      short loc_180013FDF
0x180013f8e  mov     rax, [r14]
0x180013f91  movsxd  rdx, ebp
0x180013f94  mov     rcx, [rax+8]
0x180013f98  mov     eax, ebp
0x180013f9a  mov     r8, [rcx+rdx*8]
0x180013f9e  mov     edx, 104h; unsigned __int64
0x180013fa3  imul    rcx, rax, 210h
0x180013faa  mov     eax, [r8]
0x180013fad  mov     [rcx+r11], eax
0x180013fb1  mov     eax, [r8+10h]
0x180013fb5  mov     [rcx+r11+20Ch], eax
0x180013fbd  add     rcx, 4
0x180013fc1  mov     r8, [r8+8]; unsigned __int16 *
0x180013fc5  add     rcx, r11; unsigned __int16 *
0x180013fc8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013fcd  inc     ebp
0x180013fcf  mov     ebx, eax
0x180013fd1  cmp     ebp, edi
0x180013fd3  jb      short loc_180013F8A
0x180013fd5  test    eax, eax
0x180013fd7  js      short loc_180013FDF
0x180013fd9  mov     [rsi], r11
0x180013fdc  xor     r11d, r11d
0x180013fdf  mov     rcx, r11; pv
0x180013fe2  call    cs:__imp_CoTaskMemFree
0x180013fe8  mov     eax, ebx
0x180013fea  add     rsp, 20h
0x180013fee  pop     r14
0x180013ff0  pop     rdi
0x180013ff1  pop     rsi
0x180013ff2  pop     rbp
0x180013ff3  pop     rbx
0x180013ff4  retn
```
