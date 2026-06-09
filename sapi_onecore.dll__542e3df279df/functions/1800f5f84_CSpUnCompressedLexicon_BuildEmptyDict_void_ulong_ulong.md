# CSpUnCompressedLexicon::BuildEmptyDict(void *,ulong,ulong *)

- ea: `0x1800f5f84`
- end: `0x1800f60e1`
- name: `?BuildEmptyDict@CSpUnCompressedLexicon@@AEAAJPEAXKPEAK@Z`
- size: `349`
- prototype: `__int64 __fastcall(CSpUnCompressedLexicon *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800f60e8`
- `0x1800f774c`

## callees

- `0x180079e30`
- `0x18007aae4`
- `0x1800f5f84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f5fd9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f5fe9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f5ff9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f6009`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f6019`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f6029`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f5fd9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f5fe9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f5ff9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f6009`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f6019`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f6029`

## pseudocode

```c
__int64 __fastcall CSpUnCompressedLexicon::BuildEmptyDict(
        CSpUnCompressedLexicon *this,
        _OWORD *a2,
        unsigned int a3,
        unsigned int *a4)
{
  HRESULT Guid; // ebx
  unsigned int v8; // eax
  GUID v9; // xmm1
  __int128 v10; // xmm0
  GUID v11; // xmm1
  GUID v12; // xmm0
  GUID v13; // xmm1
  GUID v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  unsigned int v17; // edi
  GUID pguid; // [rsp+30h] [rbp-59h] BYREF
  __int128 v20; // [rsp+40h] [rbp-49h] BYREF
  GUID v21; // [rsp+50h] [rbp-39h] BYREF
  GUID v22; // [rsp+60h] [rbp-29h] BYREF
  GUID v23; // [rsp+70h] [rbp-19h] BYREF
  GUID v24; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v25[28]; // [rsp+90h] [rbp+7h]

  *a4 = 0;
  memset_0(&pguid, 0, 0x7Cu);
  Guid = CoCreateGuid(&pguid);
  if ( Guid >= 0 )
  {
    Guid = CoCreateGuid((GUID *)((char *)&v20 + 4));
    if ( Guid >= 0 )
    {
      Guid = CoCreateGuid((GUID *)&v21.Data2);
      if ( Guid >= 0 )
      {
        Guid = CoCreateGuid((GUID *)&v22.Data2);
        if ( Guid >= 0 )
        {
          Guid = CoCreateGuid((GUID *)&v23.Data2);
          if ( Guid >= 0 )
            Guid = CoCreateGuid((GUID *)&v24.Data2);
        }
      }
    }
  }
  v8 = 140;
  if ( a3 < 0x8C )
    return (unsigned int)-2147201011;
  if ( Guid < 0 )
  {
    v8 = 0;
  }
  else
  {
    v9 = pguid;
    *a2 = g_guidOldLexValidationId;
    *(_DWORD *)&v25[8] = 940;
    v10 = v20;
    a2[1] = v9;
    v11 = v21;
    a2[2] = v10;
    v12 = v22;
    a2[3] = v11;
    v13 = v23;
    a2[4] = v12;
    v14 = v24;
    a2[5] = v13;
    v15 = *(_OWORD *)v25;
    a2[6] = v14;
    v16 = *(_OWORD *)&v25[12];
    a2[7] = v15;
    *(_OWORD *)((char *)a2 + 124) = v16;
  }
  v17 = v8 + 800;
  if ( v8 + 800 > a3 )
  {
    return (unsigned int)-2147201011;
  }
  else if ( Guid >= 0 )
  {
    memset_0((char *)a2 + v8, 0, 0x320u);
    *a4 = v17;
  }
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x1800f5f84  mov     [rsp-8+arg_0], rbx
0x1800f5f89  push    rbp
0x1800f5f8a  push    rsi
0x1800f5f8b  push    rdi
0x1800f5f8c  push    r14
0x1800f5f8e  push    r15
0x1800f5f90  lea     rbp, [rsp-37h]
0x1800f5f95  sub     rsp, 0C0h
0x1800f5f9c  mov     rax, cs:__security_cookie
0x1800f5fa3  xor     rax, rsp
0x1800f5fa6  mov     [rbp+57h+var_30], rax
0x1800f5faa  mov     rsi, rdx
0x1800f5fad  mov     dword ptr [r9], 0
0x1800f5fb4  xor     edx, edx; Val
0x1800f5fb6  lea     rcx, [rbp+57h+pguid]; void *
0x1800f5fba  mov     r14d, r8d
0x1800f5fbd  mov     r15, r9
0x1800f5fc0  lea     r8d, [rdx+7Ch]; Size
0x1800f5fc4  call    memset_0
0x1800f5fc9  movups  xmm0, cs:g_guidOldLexValidationId
0x1800f5fd0  lea     rcx, [rbp+57h+pguid]; pguid
0x1800f5fd4  movdqu  [rbp+57h+var_C0], xmm0
0x1800f5fd9  call    cs:__imp_CoCreateGuid
0x1800f5fdf  mov     ebx, eax
0x1800f5fe1  test    eax, eax
0x1800f5fe3  js      short loc_1800F6031
0x1800f5fe5  lea     rcx, [rbp+57h+var_9C]; pguid
0x1800f5fe9  call    cs:__imp_CoCreateGuid
0x1800f5fef  mov     ebx, eax
0x1800f5ff1  test    eax, eax
0x1800f5ff3  js      short loc_1800F6031
0x1800f5ff5  lea     rcx, [rbp+57h+var_8C]; pguid
0x1800f5ff9  call    cs:__imp_CoCreateGuid
0x1800f5fff  mov     ebx, eax
0x1800f6001  test    eax, eax
0x1800f6003  js      short loc_1800F6031
0x1800f6005  lea     rcx, [rbp+57h+var_7C]; pguid
0x1800f6009  call    cs:__imp_CoCreateGuid
0x1800f600f  mov     ebx, eax
0x1800f6011  test    eax, eax
0x1800f6013  js      short loc_1800F6031
0x1800f6015  lea     rcx, [rbp+57h+var_6C]; pguid
0x1800f6019  call    cs:__imp_CoCreateGuid
0x1800f601f  mov     ebx, eax
0x1800f6021  test    eax, eax
0x1800f6023  js      short loc_1800F6031
0x1800f6025  lea     rcx, [rbp+57h+var_5C]; pguid
0x1800f6029  call    cs:__imp_CoCreateGuid
0x1800f602f  mov     ebx, eax
0x1800f6031  mov     eax, 8Ch
0x1800f6036  cmp     r14d, eax
0x1800f6039  jb      short loc_1800F60B7
0x1800f603b  test    ebx, ebx
0x1800f603d  js      short loc_1800F608F
0x1800f603f  movaps  xmm0, [rbp+57h+var_C0]
0x1800f6043  movaps  xmm1, xmmword ptr [rbp+57h+pguid.Data1]
0x1800f6047  movups  xmmword ptr [rsi], xmm0
0x1800f604a  mov     [rbp+57h+var_48], 3ACh
0x1800f6051  movaps  xmm0, xmmword ptr [rbp-49h]
0x1800f6055  movups  xmmword ptr [rsi+10h], xmm1
0x1800f6059  movaps  xmm1, xmmword ptr [rbp-39h]
0x1800f605d  movups  xmmword ptr [rsi+20h], xmm0
0x1800f6061  movaps  xmm0, xmmword ptr [rbp-29h]
0x1800f6065  movups  xmmword ptr [rsi+30h], xmm1
0x1800f6069  movaps  xmm1, xmmword ptr [rbp-19h]
0x1800f606d  movups  xmmword ptr [rsi+40h], xmm0
0x1800f6071  movaps  xmm0, xmmword ptr [rbp-9]
0x1800f6075  movups  xmmword ptr [rsi+50h], xmm1
0x1800f6079  movaps  xmm1, xmmword ptr [rbp+7]
0x1800f607d  movups  xmmword ptr [rsi+60h], xmm0
0x1800f6081  movups  xmm0, [rbp+57h+var_44]
0x1800f6085  movups  xmmword ptr [rsi+70h], xmm1
0x1800f6089  movups  xmmword ptr [rsi+7Ch], xmm0
0x1800f608d  jmp     short loc_1800F6091
0x1800f608f  xor     eax, eax
0x1800f6091  lea     edi, [rax+320h]
0x1800f6097  cmp     edi, r14d
0x1800f609a  ja      short loc_1800F60B7
0x1800f609c  test    ebx, ebx
0x1800f609e  js      short loc_1800F60BC
0x1800f60a0  mov     ecx, eax
0x1800f60a2  xor     edx, edx; Val
0x1800f60a4  add     rcx, rsi; void *
0x1800f60a7  mov     r8d, 320h; Size
0x1800f60ad  call    memset_0
0x1800f60b2  mov     [r15], edi
0x1800f60b5  jmp     short loc_1800F60BC
0x1800f60b7  mov     ebx, 8004500Dh
0x1800f60bc  mov     eax, ebx
0x1800f60be  mov     rcx, [rbp+57h+var_30]
0x1800f60c2  xor     rcx, rsp; StackCookie
0x1800f60c5  call    __security_check_cookie
0x1800f60ca  mov     rbx, [rsp+0E0h+arg_0]
0x1800f60d2  add     rsp, 0C0h
0x1800f60d9  pop     r15
0x1800f60db  pop     r14
0x1800f60dd  pop     rdi
0x1800f60de  pop     rsi
0x1800f60df  pop     rbp
0x1800f60e0  retn
```
