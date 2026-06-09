# ClCertServerCertificateMappingAceRemove

- ea: `0x1800395a4`
- end: `0x180039812`
- name: `ClCertServerCertificateMappingAceRemove`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800323f0`

## callees

- `0x180020de8`
- `0x1800215e8`
- `0x180036b4c`
- `0x1800373e0`
- `0x180037fd0`
- `0x180038d98`
- `0x180038e20`
- `0x180038e94`
- `0x180038ff0`
- `0x1800395a4`
- `0x180039a34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180039724`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180039724`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800396c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800396c2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180039610`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180039610`

## pseudocode

```c
__int64 __fastcall ClCertServerCertificateMappingAceRemove(__int64 a1, _QWORD *a2)
{
  const WCHAR *v3; // rdi
  const WCHAR *v4; // r14
  unsigned int v5; // eax
  void *v6; // rsi
  unsigned int v7; // ebx
  const WCHAR *v8; // r12
  __int64 v9; // r13
  unsigned int v11; // ebx
  __int64 v12; // rcx
  unsigned int v13; // eax
  _QWORD *v14; // rcx
  int v15; // edx
  LPCWSTR lpValueName; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-30h] BYREF
  UCHAR v18[8]; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  __int64 v20; // [rsp+50h] [rbp-18h]
  unsigned int v21; // [rsp+B0h] [rbp+48h]
  unsigned int v23; // [rsp+C0h] [rbp+58h]
  void *v24; // [rsp+C8h] [rbp+60h] BYREF

  *(_QWORD *)v18 = 0;
  v3 = 0;
  lpValueName = 0;
  v4 = 0;
  v5 = *(_DWORD *)(a1 + 28);
  v6 = 0;
  v7 = *(_DWORD *)(a1 + 24);
  v8 = *(const WCHAR **)a1;
  v9 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 8) = 0;
  *a2 = 0;
  v20 = 0;
  lpSubKey = 0;
  hKey = 0;
  v24 = 0;
  v21 = v5;
  v23 = v7;
  if ( !InitOnceExecuteOnce(&ClCertInitOnce, ClCertInitOnceFn, 0, 0) )
    return 1359;
  v11 = ClCertValidateAce(v8, 0, (UCHAR)v18);
  if ( !v11 )
  {
    if ( v23 == 1 )
      v9 = *(_QWORD *)v18;
    v11 = ClCertCalculateCertSid(v21, v23, v9, &lpValueName);
    if ( v11 )
    {
      v3 = lpValueName;
      goto LABEL_28;
    }
    v13 = ClCertRegConcatKeyToPath(v12, v8, &lpSubKey);
    v3 = lpValueName;
    v11 = v13;
    v4 = lpSubKey;
    if ( !v13 )
    {
      v11 = ClCertRegContainsValue(lpSubKey, lpValueName);
      if ( !v11 )
      {
        v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 3u, &hKey);
        if ( v11 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            v15 = 19;
LABEL_14:
            WPP_SF_Sd(v14[2], v15, (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids, (_DWORD)v8, v11);
          }
        }
        else
        {
          v11 = RegDeleteValueW(hKey, v3);
          if ( !v11 )
          {
            v11 = ClCertCreateOutputAce(a1, v9, v20, &v24);
            if ( v11 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_053b19d310c5352633ee666709ba12ba_Traceguids, v11);
              }
              v6 = v24;
            }
            else
            {
              *a2 = v24;
            }
            goto LABEL_28;
          }
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            v15 = 20;
            goto LABEL_14;
          }
        }
      }
    }
  }
LABEL_28:
  ClCertLocalFree(*(_QWORD *)v18);
  ClCertLocalFree(v3);
  ClCertLocalFree(v4);
  if ( hKey )
    ClCertRegCloseKey();
  ClCertLocalFree(v20);
  ClCertFreeOutputAce(v6);
  return v11;
}

```

## disassembly

```asm
0x1800395a4  mov     [rsp-40h+arg_8], rdx
0x1800395a9  push    rbp
0x1800395aa  push    rbx
0x1800395ab  push    rsi
0x1800395ac  push    rdi
0x1800395ad  push    r12
0x1800395af  push    r13
0x1800395b1  push    r14
0x1800395b3  push    r15
0x1800395b5  mov     rbp, rsp
0x1800395b8  sub     rsp, 68h
0x1800395bc  mov     r15, rcx
0x1800395bf  xor     r9d, r9d; Context
0x1800395c2  xor     ecx, ecx
0x1800395c4  xor     r8d, r8d; Parameter
0x1800395c7  mov     qword ptr [rbp+var_28], rcx
0x1800395cb  mov     edi, ecx
0x1800395cd  mov     [rbp+lpValueName], rcx
0x1800395d1  mov     r14d, ecx
0x1800395d4  mov     eax, [r15+1Ch]
0x1800395d8  mov     esi, ecx
0x1800395da  mov     ebx, [r15+18h]
0x1800395de  mov     r12, [r15]
0x1800395e1  mov     r13, [r15+10h]
0x1800395e5  mov     [r15+8], rcx
0x1800395e9  mov     [rdx], rcx
0x1800395ec  lea     rdx, ClCertInitOnceFn; InitFn
0x1800395f3  mov     [rbp+var_18], rcx
0x1800395f7  mov     [rbp+lpSubKey], rcx
0x1800395fb  mov     [rbp+hKey], rcx
0x1800395ff  mov     [rbp+arg_18], rcx
0x180039603  lea     rcx, ClCertInitOnce; InitOnce
0x18003960a  mov     [rbp+arg_0], eax
0x18003960d  mov     [rbp+arg_10], ebx
0x180039610  call    cs:__imp_InitOnceExecuteOnce
0x180039616  test    eax, eax
0x180039618  jnz     short loc_180039624
0x18003961a  mov     eax, 54Fh
0x18003961f  jmp     loc_180039801
0x180039624  mov     edx, [rbp+arg_0]
0x180039627  lea     rax, [rbp+var_28]
0x18003962b  mov     qword ptr [rsp+68h+pbOutput], rax; pbOutput
0x180039630  mov     r9, r13
0x180039633  mov     r8d, ebx
0x180039636  mov     [rsp+68h+phkResult], rsi; __int64
0x18003963b  mov     rcx, r12; lpValue
0x18003963e  call    ClCertValidateAce
0x180039643  mov     ebx, eax
0x180039645  test    eax, eax
0x180039647  jnz     loc_1800397C7
0x18003964d  mov     edx, [rbp+arg_10]
0x180039650  lea     r9, [rbp+lpValueName]
0x180039654  mov     ecx, [rbp+arg_0]
0x180039657  cmp     edx, 1
0x18003965a  cmovz   r13, qword ptr [rbp+var_28]
0x18003965f  mov     r8, r13
0x180039662  call    ClCertCalculateCertSid
0x180039667  mov     ebx, eax
0x180039669  test    eax, eax
0x18003966b  jnz     loc_1800397C3
0x180039671  lea     r8, [rbp+lpSubKey]
0x180039675  mov     rdx, r12
0x180039678  call    ClCertRegConcatKeyToPath
0x18003967d  mov     rdi, [rbp+lpValueName]
0x180039681  mov     ebx, eax
0x180039683  mov     r14, [rbp+lpSubKey]
0x180039687  test    eax, eax
0x180039689  jnz     loc_1800397C7
0x18003968f  lea     r8, [rbp+var_18]
0x180039693  mov     rdx, rdi; lpValue
0x180039696  mov     rcx, r14; lpSubKey
0x180039699  call    ClCertRegContainsValue
0x18003969e  mov     ebx, eax
0x1800396a0  test    eax, eax
0x1800396a2  jnz     loc_1800397C7
0x1800396a8  lea     rax, [rbp+hKey]
0x1800396ac  xor     r8d, r8d; ulOptions
0x1800396af  lea     r9d, [rbx+3]; samDesired
0x1800396b3  mov     [rsp+68h+phkResult], rax; phkResult
0x1800396b8  mov     rdx, r14; lpSubKey
0x1800396bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800396c2  call    cs:__imp_RegOpenKeyExW
0x1800396c8  mov     ebx, eax
0x1800396ca  test    eax, eax
0x1800396cc  jz      short loc_18003971D
0x1800396ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396d5  lea     rax, WPP_GLOBAL_Control
0x1800396dc  cmp     rcx, rax
0x1800396df  jz      loc_1800397C7
0x1800396e5  test    dword ptr [rcx+1Ch], 800h
0x1800396ec  jz      loc_1800397C7
0x1800396f2  cmp     byte ptr [rcx+19h], 1
0x1800396f6  jb      loc_1800397C7
0x1800396fc  mov     edx, 13h
0x180039701  mov     rcx, [rcx+10h]
0x180039705  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x18003970c  mov     r9, r12
0x18003970f  mov     dword ptr [rsp+68h+phkResult], ebx
0x180039713  call    WPP_SF_Sd
0x180039718  jmp     loc_1800397C7
0x18003971d  mov     rcx, [rbp+hKey]; hKey
0x180039721  mov     rdx, rdi; lpValueName
0x180039724  call    cs:__imp_RegDeleteValueW
0x18003972a  mov     ebx, eax
0x18003972c  test    eax, eax
0x18003972e  jz      short loc_18003975D
0x180039730  mov     rcx, cs:WPP_GLOBAL_Control
0x180039737  lea     rax, WPP_GLOBAL_Control
0x18003973e  cmp     rcx, rax
0x180039741  jz      loc_1800397C7
0x180039747  test    dword ptr [rcx+1Ch], 800h
0x18003974e  jz      short loc_1800397C7
0x180039750  cmp     byte ptr [rcx+19h], 1
0x180039754  jb      short loc_1800397C7
0x180039756  mov     edx, 14h
0x18003975b  jmp     short loc_180039701
0x18003975d  mov     r8, [rbp+var_18]
0x180039761  lea     r9, [rbp+arg_18]
0x180039765  mov     rdx, r13
0x180039768  mov     rcx, r15
0x18003976b  call    ClCertCreateOutputAce
0x180039770  mov     ebx, eax
0x180039772  test    eax, eax
0x180039774  jz      short loc_1800397B6
0x180039776  mov     rcx, cs:WPP_GLOBAL_Control
0x18003977d  lea     rax, WPP_GLOBAL_Control
0x180039784  cmp     rcx, rax
0x180039787  jz      short loc_1800397B0
0x180039789  test    dword ptr [rcx+1Ch], 800h
0x180039790  jz      short loc_1800397B0
0x180039792  cmp     byte ptr [rcx+19h], 1
0x180039796  jb      short loc_1800397B0
0x180039798  mov     rcx, [rcx+10h]
0x18003979c  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x1800397a3  mov     edx, 15h
0x1800397a8  mov     r9d, ebx
0x1800397ab  call    WPP_SF_d
0x1800397b0  mov     rsi, [rbp+arg_18]
0x1800397b4  jmp     short loc_1800397C7
0x1800397b6  mov     rcx, [rbp+arg_8]
0x1800397ba  mov     rax, [rbp+arg_18]
0x1800397be  mov     [rcx], rax
0x1800397c1  jmp     short loc_1800397C7
0x1800397c3  mov     rdi, [rbp+lpValueName]
0x1800397c7  mov     rcx, qword ptr [rbp+var_28]
0x1800397cb  call    ClCertLocalFree
0x1800397d0  mov     rcx, rdi
0x1800397d3  call    ClCertLocalFree
0x1800397d8  mov     rcx, r14
0x1800397db  call    ClCertLocalFree
0x1800397e0  mov     rcx, [rbp+hKey]
0x1800397e4  test    rcx, rcx
0x1800397e7  jz      short loc_1800397EE
0x1800397e9  call    ClCertRegCloseKey
0x1800397ee  mov     rcx, [rbp+var_18]
0x1800397f2  call    ClCertLocalFree
0x1800397f7  mov     rcx, rsi; hMem
0x1800397fa  call    ClCertFreeOutputAce
0x1800397ff  mov     eax, ebx
0x180039801  add     rsp, 68h
0x180039805  pop     r15
0x180039807  pop     r14
0x180039809  pop     r13
0x18003980b  pop     r12
0x18003980d  pop     rdi
0x18003980e  pop     rsi
0x18003980f  pop     rbx
0x180039810  pop     rbp
0x180039811  retn
```
