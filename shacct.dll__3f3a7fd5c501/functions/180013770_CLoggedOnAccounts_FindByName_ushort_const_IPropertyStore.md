# CLoggedOnAccounts::FindByName(ushort const *,IPropertyStore * *)

- ea: `0x180013770`
- end: `0x1800139ab`
- name: `?FindByName@CLoggedOnAccounts@@UEAAJPEBGPEAPEAUIPropertyStore@@@Z`
- size: `571`
- prototype: `int(CLoggedOnAccounts *__hidden this, const unsigned __int16 *, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bcc0`
- `0x18000c240`
- `0x180013770`
- `0x180016880`
- `0x1800169c4`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001389d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800138e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013913`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001389d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800138e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013913`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800137f6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800137f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013948`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013948`

## pseudocode

```c
__int64 __fastcall CLoggedOnAccounts::FindByName(
        CLoggedOnAccounts *this,
        unsigned __int16 *a2,
        struct IPropertyStore **a3)
{
  int v5; // ebx
  __int64 v6; // rax
  BOOL v7; // edi
  int v8; // eax
  struct IPropertyStore *v9; // rcx
  struct IPropertyStore *v11; // [rsp+30h] [rbp-D0h] BYREF
  DWORD nSize; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+3Ch] [rbp-C4h] BYREF
  LPCWCH v14; // [rsp+40h] [rbp-C0h] BYREF
  LPCWCH lpString1; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[20]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v18[256]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR String2[264]; // [rsp+280h] [rbp+180h] BYREF

  v5 = -2147024809;
  if ( a2 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v5 = SHParseUserName(a2, v18, 0x100u, String2);
      if ( v5 >= 0 )
      {
        nSize = 16;
        if ( !GetComputerNameW(Buffer, &nSize) )
          return (unsigned int)ResultFromKnownLastError();
        v6 = *(_QWORD *)this;
        v16 = 0;
        v5 = (*(__int64 (__fastcall **)(CLoggedOnAccounts *, __int64 *))(v6 + 24))(this, &v16);
        if ( v5 >= 0 )
        {
          v11 = 0;
          v7 = 0;
          v13 = 0;
          while ( 1 )
          {
            if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct IPropertyStore **, int *))(*(_QWORD *)v16 + 24LL))(
                   v16,
                   1,
                   &v11,
                   &v13) )
            {
              v5 = -2147024809;
LABEL_23:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              return (unsigned int)v5;
            }
            lpString1 = 0;
            if ( (int)IPropertyStore_GetString(v11, &PKEY_SAM_Name, &lpString1) >= 0 )
              break;
LABEL_20:
            ((void (__fastcall *)(struct IPropertyStore *))v11->lpVtbl->Release)(v11);
            if ( v7 )
              goto LABEL_23;
          }
          if ( CompareStringOrdinal(lpString1, -1, String2, -1, 1) == 2 )
          {
            v14 = 0;
            IPropertyStore_GetString(v11, &PKEY_SAM_Domain, &v14);
            if ( !v18[0] )
            {
              if ( !v14 || CompareStringOrdinal(v14, -1, Buffer, -1, 1) == 2 )
              {
                v7 = 1;
                goto LABEL_16;
              }
              if ( !v18[0] )
                goto LABEL_18;
            }
            if ( !v14 )
            {
LABEL_18:
              v7 = 0;
              goto LABEL_19;
            }
            v8 = CompareStringOrdinal(v14, -1, v18, -1, 1);
            v7 = v8 == 2;
            if ( v8 == 2 )
            {
LABEL_16:
              v9 = v11;
              *a3 = v11;
              ((void (__fastcall *)(struct IPropertyStore *))v9->lpVtbl->AddRef)(v9);
            }
          }
LABEL_19:
          CoTaskMemFree((LPVOID)lpString1);
          goto LABEL_20;
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013770  push    rbp
0x180013772  push    rbx
0x180013773  push    rsi
0x180013774  push    rdi
0x180013775  push    r12
0x180013777  push    r14
0x180013779  push    r15
0x18001377b  lea     rbp, [rsp-3A0h]
0x180013783  sub     rsp, 4A0h
0x18001378a  mov     rax, cs:__security_cookie
0x180013791  xor     rax, rsp
0x180013794  mov     [rbp+3D0h+var_40], rax
0x18001379b  xor     r14d, r14d
0x18001379e  mov     rsi, r8
0x1800137a1  mov     rax, rdx
0x1800137a4  mov     rdi, rcx
0x1800137a7  mov     ebx, 80070057h
0x1800137ac  test    rdx, rdx
0x1800137af  jz      loc_180013988
0x1800137b5  test    r8, r8
0x1800137b8  jz      loc_180013988
0x1800137be  mov     [r8], r14
0x1800137c1  lea     r9, [rbp+3D0h+String2]; unsigned __int16 *
0x1800137c8  mov     r8d, 100h; unsigned __int64
0x1800137ce  lea     rdx, [rbp+3D0h+var_450]; unsigned __int16 *
0x1800137d2  mov     rcx, rax; unsigned __int16 *
0x1800137d5  call    SHParseUserName
0x1800137da  mov     ebx, eax
0x1800137dc  test    eax, eax
0x1800137de  js      loc_180013988
0x1800137e4  lea     rdx, [rsp+4D0h+nSize]; nSize
0x1800137e9  mov     [rsp+4D0h+nSize], 10h
0x1800137f1  lea     rcx, [rsp+4D0h+Buffer]; lpBuffer
0x1800137f6  call    cs:__imp_GetComputerNameW
0x1800137fc  lea     r15d, [r14+1]
0x180013800  cmp     eax, r15d
0x180013803  jnz     loc_180013981
0x180013809  mov     rax, [rdi]
0x18001380c  lea     rdx, [rsp+4D0h+var_480]
0x180013811  mov     rcx, rdi
0x180013814  mov     [rsp+4D0h+var_480], r14
0x180013819  mov     rax, [rax+18h]
0x18001381d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013822  mov     ebx, eax
0x180013824  test    eax, eax
0x180013826  js      loc_180013988
0x18001382c  mov     [rsp+4D0h+var_4A0], r14
0x180013831  mov     edi, r14d
0x180013834  mov     [rsp+4D0h+var_494], r14d
0x180013839  or      r12d, 0FFFFFFFFh
0x18001383d  mov     rcx, [rsp+4D0h+var_480]
0x180013842  lea     r9, [rsp+4D0h+var_494]
0x180013847  lea     r8, [rsp+4D0h+var_4A0]
0x18001384c  mov     edx, r15d
0x18001384f  mov     rax, [rcx]
0x180013852  mov     rax, [rax+18h]
0x180013856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001385b  test    eax, eax
0x18001385d  jnz     loc_180013969
0x180013863  mov     rcx, [rsp+4D0h+var_4A0]
0x180013868  lea     r8, [rsp+4D0h+lpString1]
0x18001386d  lea     rdx, PKEY_SAM_Name
0x180013874  mov     [rsp+4D0h+lpString1], r14
0x180013879  call    IPropertyStore_GetString
0x18001387e  test    eax, eax
0x180013880  js      loc_18001394E
0x180013886  mov     rcx, [rsp+4D0h+lpString1]; lpString1
0x18001388b  lea     r8, [rbp+3D0h+String2]; lpString2
0x180013892  mov     r9d, r12d; cchCount2
0x180013895  mov     [rsp+4D0h+bIgnoreCase], r15d; bIgnoreCase
0x18001389a  mov     edx, r12d; cchCount1
0x18001389d  call    cs:__imp_CompareStringOrdinal
0x1800138a3  cmp     eax, 2
0x1800138a6  jnz     loc_180013943
0x1800138ac  mov     rcx, [rsp+4D0h+var_4A0]
0x1800138b1  lea     r8, [rsp+4D0h+var_490]
0x1800138b6  lea     rdx, PKEY_SAM_Domain
0x1800138bd  mov     [rsp+4D0h+var_490], r14
0x1800138c2  call    IPropertyStore_GetString
0x1800138c7  cmp     [rbp+3D0h+var_450], r14w
0x1800138cc  jnz     short loc_1800138FA
0x1800138ce  mov     rcx, [rsp+4D0h+var_490]; lpString1
0x1800138d3  test    rcx, rcx
0x1800138d6  jz      short loc_18001393B
0x1800138d8  mov     r9d, r12d; cchCount2
0x1800138db  mov     [rsp+4D0h+bIgnoreCase], r15d; bIgnoreCase
0x1800138e0  lea     r8, [rsp+4D0h+Buffer]; lpString2
0x1800138e5  mov     edx, r12d; cchCount1
0x1800138e8  call    cs:__imp_CompareStringOrdinal
0x1800138ee  cmp     eax, 2
0x1800138f1  jz      short loc_18001393B
0x1800138f3  cmp     [rbp+3D0h+var_450], r14w
0x1800138f8  jz      short loc_180013940
0x1800138fa  mov     rcx, [rsp+4D0h+var_490]; lpString1
0x1800138ff  test    rcx, rcx
0x180013902  jz      short loc_180013940
0x180013904  mov     r9d, r12d; cchCount2
0x180013907  mov     [rsp+4D0h+bIgnoreCase], r15d; bIgnoreCase
0x18001390c  lea     r8, [rbp+3D0h+var_450]; lpString2
0x180013910  mov     edx, r12d; cchCount1
0x180013913  call    cs:__imp_CompareStringOrdinal
0x180013919  cmp     eax, 2
0x18001391c  mov     edi, r14d
0x18001391f  setz    dil
0x180013923  jnz     short loc_180013943
0x180013925  mov     rcx, [rsp+4D0h+var_4A0]
0x18001392a  mov     [rsi], rcx
0x18001392d  mov     rax, [rcx]
0x180013930  mov     rax, [rax+8]
0x180013934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013939  jmp     short loc_180013943
0x18001393b  mov     edi, r15d
0x18001393e  jmp     short loc_180013925
0x180013940  mov     edi, r14d
0x180013943  mov     rcx, [rsp+4D0h+lpString1]; pv
0x180013948  call    cs:__imp_CoTaskMemFree
0x18001394e  mov     rcx, [rsp+4D0h+var_4A0]
0x180013953  mov     rax, [rcx]
0x180013956  mov     rax, [rax+10h]
0x18001395a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001395f  test    edi, edi
0x180013961  jz      loc_18001383D
0x180013967  jmp     short loc_18001396E
0x180013969  mov     ebx, 80070057h
0x18001396e  mov     rcx, [rsp+4D0h+var_480]
0x180013973  mov     rax, [rcx]
0x180013976  mov     rax, [rax+10h]
0x18001397a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001397f  jmp     short loc_180013988
0x180013981  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180013986  mov     ebx, eax
0x180013988  mov     eax, ebx
0x18001398a  mov     rcx, [rbp+3D0h+var_40]
0x180013991  xor     rcx, rsp; StackCookie
0x180013994  call    __security_check_cookie
0x180013999  add     rsp, 4A0h
0x1800139a0  pop     r15
0x1800139a2  pop     r14
0x1800139a4  pop     r12
0x1800139a6  pop     rdi
0x1800139a7  pop     rsi
0x1800139a8  pop     rbx
0x1800139a9  pop     rbp
0x1800139aa  retn
```
