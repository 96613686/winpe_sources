# _BasicApiWrapper(_PROFILE_FOLDER_ID,ushort const *,ushort *,ulong *)

- ea: `0x180006fe0`
- end: `0x18000711d`
- name: `?_BasicApiWrapper@@YAHW4_PROFILE_FOLDER_ID@@PEBGPEAGPEAK@Z`
- size: `317`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *, _DWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180006f80`
- `0x180006fa0`
- `0x180006fc0`
- `0x180013f80`
- `0x180014070`
- `0x180014160`

## callees

- `0x180006fe0`
- `0x18000d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800070d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800070ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800070d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800070ff`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000702c`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800070c8`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000702c`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800070c8`

## pseudocode

```c
__int64 __fastcall _BasicApiWrapper(__int64 a1, __int64 a2, _WORD *a3, _DWORD *a4)
{
  _WORD *v5; // rbx
  unsigned int v7; // r15d
  __int64 v8; // rbp
  int BasicProfileFolderPath; // edi
  __int64 v10; // rcx
  _WORD *v12; // rax
  _BYTE v13[528]; // [rsp+20h] [rbp-258h] BYREF

  v5 = a3;
  v7 = a1;
  if ( !a4 )
  {
    LOWORD(BasicProfileFolderPath) = 87;
    goto LABEL_15;
  }
  if ( a3 && *a4 )
  {
    v8 = 0x7FFFFFFF;
    BasicProfileFolderPath = GetBasicProfileFolderPath(a1, a2, a3, (unsigned int)*a4);
    if ( BasicProfileFolderPath >= 0 )
    {
      v10 = 0x7FFFFFFF;
      do
      {
        if ( !*v5 )
          break;
        ++v5;
        --v10;
      }
      while ( v10 );
      BasicProfileFolderPath = -2147024809;
      if ( v10 )
      {
        BasicProfileFolderPath = 0;
        *a4 = 0x80000000 - v10;
      }
    }
    if ( BasicProfileFolderPath != -2147024774 )
    {
      if ( BasicProfileFolderPath >= 0 )
        return 1;
      goto LABEL_15;
    }
    if ( *a4 >= 0x104u )
    {
LABEL_15:
      SetLastError((unsigned __int16)BasicProfileFolderPath);
      return 0;
    }
  }
  else
  {
    LOWORD(BasicProfileFolderPath) = 122;
    *a4 = 0;
    v8 = 0x7FFFFFFF;
  }
  if ( (int)GetBasicProfileFolderPath(v7, a2, v13, 260) < 0 )
    goto LABEL_15;
  v12 = v13;
  while ( *v12 )
  {
    ++v12;
    if ( !--v8 )
      goto LABEL_15;
  }
  *a4 = 0x80000000 - v8;
  SetLastError((unsigned __int16)BasicProfileFolderPath);
  return 0;
}

```

## disassembly

```asm
0x180006fe0  push    rbx
0x180006fe2  push    rbp
0x180006fe3  push    rsi
0x180006fe4  push    rdi
0x180006fe5  push    r12
0x180006fe7  push    r14
0x180006fe9  push    r15
0x180006feb  sub     rsp, 240h
0x180006ff2  mov     rax, cs:__security_cookie
0x180006ff9  xor     rax, rsp
0x180006ffc  mov     [rsp+278h+var_48], rax
0x180007004  mov     rsi, r9
0x180007007  mov     rbx, r8
0x18000700a  mov     r12, rdx
0x18000700d  mov     r15d, ecx
0x180007010  test    r9, r9
0x180007013  jz      loc_180007116
0x180007019  test    rbx, rbx
0x18000701c  jz      loc_1800070A2
0x180007022  mov     eax, [r9]
0x180007025  test    eax, eax
0x180007027  jz      short loc_1800070A2
0x180007029  mov     r9d, eax
0x18000702c  call    cs:__imp_GetBasicProfileFolderPath
0x180007032  mov     ebp, 7FFFFFFFh
0x180007037  mov     r14d, 80000000h
0x18000703d  mov     edi, eax
0x18000703f  test    eax, eax
0x180007041  js      short loc_18000706B
0x180007043  mov     ecx, ebp
0x180007045  cmp     word ptr [rbx], 0
0x180007049  jz      short loc_180007055
0x18000704b  add     rbx, 2
0x18000704f  sub     rcx, 1
0x180007053  jnz     short loc_180007045
0x180007055  xor     eax, eax
0x180007057  mov     edi, 80070057h
0x18000705c  test    rcx, rcx
0x18000705f  cmovnz  edi, eax
0x180007062  jz      short loc_18000706B
0x180007064  mov     eax, r14d
0x180007067  sub     eax, ecx
0x180007069  mov     [rsi], eax
0x18000706b  cmp     edi, 8007007Ah
0x180007071  jz      loc_18000710C
0x180007077  test    edi, edi
0x180007079  js      short loc_1800070D2
0x18000707b  mov     eax, 1
0x180007080  mov     rcx, [rsp+278h+var_48]
0x180007088  xor     rcx, rsp; StackCookie
0x18000708b  call    __security_check_cookie
0x180007090  add     rsp, 240h
0x180007097  pop     r15
0x180007099  pop     r14
0x18000709b  pop     r12
0x18000709d  pop     rdi
0x18000709e  pop     rsi
0x18000709f  pop     rbp
0x1800070a0  pop     rbx
0x1800070a1  retn
0x1800070a2  xor     eax, eax
0x1800070a4  mov     edi, 8007007Ah
0x1800070a9  mov     [r9], eax
0x1800070ac  mov     ebp, 7FFFFFFFh
0x1800070b1  mov     r14d, 80000000h
0x1800070b7  mov     r9d, 104h
0x1800070bd  lea     r8, [rsp+278h+var_258]
0x1800070c2  mov     rdx, r12
0x1800070c5  mov     ecx, r15d
0x1800070c8  call    cs:__imp_GetBasicProfileFolderPath
0x1800070ce  test    eax, eax
0x1800070d0  jns     short loc_1800070DF
0x1800070d2  movzx   ecx, di; dwErrCode
0x1800070d5  call    cs:__imp_SetLastError
0x1800070db  xor     eax, eax
0x1800070dd  jmp     short loc_180007080
0x1800070df  lea     rax, [rsp+278h+var_258]
0x1800070e4  cmp     word ptr [rax], 0
0x1800070e8  jz      short loc_1800070F6
0x1800070ea  add     rax, 2
0x1800070ee  sub     rbp, 1
0x1800070f2  jnz     short loc_1800070E4
0x1800070f4  jmp     short loc_1800070D2
0x1800070f6  sub     r14d, ebp
0x1800070f9  movzx   ecx, di; dwErrCode
0x1800070fc  mov     [rsi], r14d
0x1800070ff  call    cs:__imp_SetLastError
0x180007105  xor     eax, eax
0x180007107  jmp     loc_180007080
0x18000710c  cmp     dword ptr [rsi], 104h
0x180007112  jnb     short loc_1800070D2
0x180007114  jmp     short loc_1800070B7
0x180007116  mov     edi, 80070057h
0x18000711b  jmp     short loc_1800070D2
```
