# GetUserProfileListRootKeyName(ushort * *,int *)

- ea: `0x180003e90`
- end: `0x18000409c`
- name: `?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z`
- size: `524`
- prototype: `__int64 __fastcall(unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002a40`
- `0x180003480`

## callees

- `0x180003e90`
- `0x1800040b0`
- `0x180007e00`
- `0x18000db08`
- `0x18000efe0`
- `0x180019204`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fcb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003f30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003f30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003ed7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003ed7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004038`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004038`

## string_xrefs

- `0x180003ffe`: `OneCore\internal\DS\inc\profiles\sid.h`

## pseudocode

```c
__int64 __fastcall GetUserProfileListRootKeyName(unsigned __int16 **a1, int *a2)
{
  void *v3; // rsi
  int v4; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // r8
  int v7; // ebx
  __int64 v8; // rcx
  const wchar_t *v9; // rdx
  __int64 v10; // r9
  __int64 v11; // r10
  unsigned __int16 *v12; // r11
  __int64 v13; // r14
  HANDLE v14; // rax
  __int64 v16; // rdx
  int v17; // ebx
  int v18; // [rsp+20h] [rbp-48h]
  _QWORD v19[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  *a1 = 0;
  memset(v19, 0, 24);
  hKey = 0;
  v3 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\ProfileList", 0, 0x20019u, &hKey);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  if ( v4 >= 0 )
  {
    v17 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
            v19,
            hKey,
            L"RedirectionKey");
    RegCloseKey(hKey);
    if ( v17 >= 0 )
    {
      v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(v19, a1);
      if ( v7 < 0 )
      {
        v16 = 82;
        goto LABEL_18;
      }
      v3 = (void *)v19[0];
      goto LABEL_13;
    }
    v3 = (void *)v19[0];
  }
  ProcessHeap = GetProcessHeap();
  *a1 = 0;
  if ( !is_mul_ok(0x39u, 2u) )
  {
    v7 = -2147024362;
    goto LABEL_17;
  }
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, (0x39 * (unsigned __int128)2uLL) >> 64, 0x72u);
  *a1 = v6;
  if ( !v6 )
  {
    v7 = -2147024882;
LABEL_17:
    v16 = 90;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"OneCore\\internal\\DS\\inc\\profiles\\sid.h",
      (const char *)(unsigned int)v7,
      v18);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v19);
    return (unsigned int)v7;
  }
  v8 = 56;
  v9 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
  v10 = 57;
  v11 = 0;
  v12 = v6;
  while ( v8 && *v9 )
  {
    *v6++ = *v9++;
    --v8;
    ++v11;
    if ( !--v10 )
    {
      *(v6 - 1) = 0;
      goto LABEL_13;
    }
  }
  v13 = 57 - v11;
  *v6 = 0;
  if ( (unsigned __int64)(57 - v11) > 1 && (unsigned __int64)(2 * v13) > 2 )
    memset_0(&v12[v11 + 1], 0, 2 * v13 - 2);
LABEL_13:
  if ( v3 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180003e90  mov     r11, rsp
0x180003e93  mov     [r11+10h], rdx
0x180003e97  push    rbp
0x180003e98  push    rsi
0x180003e99  push    rdi
0x180003e9a  sub     rsp, 50h
0x180003e9e  xor     ebp, ebp
0x180003ea0  lea     rax, [r11+10h]
0x180003ea4  mov     [rcx], rbp
0x180003ea7  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Pro"...
0x180003eae  mov     rdi, rcx
0x180003eb1  mov     [r11-38h], rbp
0x180003eb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003ebc  mov     [r11-30h], rbp
0x180003ec0  mov     r9d, 20019h; samDesired
0x180003ec6  mov     [r11-28h], rbp
0x180003eca  xor     r8d, r8d; ulOptions
0x180003ecd  mov     [r11+10h], rbp
0x180003ed1  mov     esi, ebp
0x180003ed3  mov     [r11-48h], rax
0x180003ed7  call    cs:__imp_RegOpenKeyExW
0x180003ede  nop     dword ptr [rax+rax+00h]
0x180003ee3  test    eax, eax
0x180003ee5  jle     short loc_180003EEF
0x180003ee7  movzx   eax, ax
0x180003eea  or      eax, 80070000h
0x180003eef  mov     [rsp+68h+arg_0], rbx
0x180003ef4  mov     [rsp+68h+arg_10], r14
0x180003efc  test    eax, eax
0x180003efe  jns     loc_18000401B
0x180003f04  call    cs:__imp_GetProcessHeap
0x180003f0b  nop     dword ptr [rax+rax+00h]
0x180003f10  mov     r14d, 39h ; '9'
0x180003f16  mov     [rdi], rbp
0x180003f19  mov     rcx, rax; hHeap
0x180003f1c  mov     eax, 2
0x180003f21  mul     r14
0x180003f24  test    rdx, rdx
0x180003f27  jnz     loc_180003FEF
0x180003f2d  mov     r8, rax; dwBytes
0x180003f30  call    cs:__imp_HeapAlloc
0x180003f37  nop     dword ptr [rax+rax+00h]
0x180003f3c  mov     r8, rax
0x180003f3f  mov     [rdi], rax
0x180003f42  test    r8, r8
0x180003f45  mov     ebx, ebp
0x180003f47  mov     eax, 8007000Eh
0x180003f4c  cmovz   ebx, eax
0x180003f4f  jz      loc_180003FF4
0x180003f55  mov     ecx, 38h ; '8'
0x180003f5a  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003f61  mov     r9d, r14d
0x180003f64  mov     r10, rbp
0x180003f67  mov     r11, r8
0x180003f6a  nop     word ptr [rax+rax+00h]
0x180003f70  test    rcx, rcx
0x180003f73  jz      short loc_180003FA1
0x180003f75  movzx   eax, word ptr [rdx]
0x180003f78  test    ax, ax
0x180003f7b  jz      short loc_180003F9C
0x180003f7d  mov     [r8], ax
0x180003f81  add     rdx, 2
0x180003f85  add     r8, 2
0x180003f89  dec     rcx
0x180003f8c  inc     r10
0x180003f8f  sub     r9, 1
0x180003f93  jnz     short loc_180003F70
0x180003f95  mov     [r8-2], bp
0x180003f9a  jmp     short loc_180003FB2
0x180003f9c  test    r9, r9
0x180003f9f  jz      short loc_180003F95
0x180003fa1  sub     r14, r10
0x180003fa4  mov     [r8], bp
0x180003fa8  cmp     r14, 1
0x180003fac  ja      loc_180004076
0x180003fb2  test    rsi, rsi
0x180003fb5  jz      short loc_180003FD7
0x180003fb7  call    cs:__imp_GetProcessHeap
0x180003fbe  nop     dword ptr [rax+rax+00h]
0x180003fc3  mov     r8, rsi; lpMem
0x180003fc6  xor     edx, edx; dwFlags
0x180003fc8  mov     rcx, rax; hHeap
0x180003fcb  call    cs:__imp_HeapFree
0x180003fd2  nop     dword ptr [rax+rax+00h]
0x180003fd7  xor     eax, eax
0x180003fd9  mov     r14, [rsp+68h+arg_10]
0x180003fe1  mov     rbx, [rsp+68h+arg_0]
0x180003fe6  add     rsp, 50h
0x180003fea  pop     rdi
0x180003feb  pop     rsi
0x180003fec  pop     rbp
0x180003fed  retn
0x180003fef  mov     ebx, 80070216h
0x180003ff4  mov     edx, 5Ah ; 'Z'; void *
0x180003ff9  mov     rcx, [rsp+68h]; this
0x180003ffe  lea     r8, aOnecoreInterna_2; "OneCore\\internal\\DS\\inc\\profiles\\s"...
0x180004005  mov     r9d, ebx; char *
0x180004008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000400d  lea     rcx, [rsp+68h+var_38]
0x180004012  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180004017  mov     eax, ebx
0x180004019  jmp     short loc_180003FD9
0x18000401b  mov     rdx, [rsp+68h+hKey]
0x180004020  lea     r8, aRedirectionkey; "RedirectionKey"
0x180004027  lea     rcx, [rsp+68h+var_38]
0x18000402c  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180004031  mov     rcx, [rsp+68h+hKey]; hKey
0x180004036  mov     ebx, eax
0x180004038  call    cs:__imp_RegCloseKey
0x18000403f  nop     dword ptr [rax+rax+00h]
0x180004044  test    ebx, ebx
0x180004046  jns     short loc_180004052
0x180004048  mov     rsi, [rsp+68h+var_38]
0x18000404d  jmp     loc_180003F04
0x180004052  mov     rdx, rdi
0x180004055  lea     rcx, [rsp+68h+var_38]
0x18000405a  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x18000405f  mov     ebx, eax
0x180004061  test    eax, eax
0x180004063  jns     short loc_18000406C
0x180004065  mov     edx, 52h ; 'R'
0x18000406a  jmp     short loc_180003FF9
0x18000406c  mov     rsi, [rsp+68h+var_38]
0x180004071  jmp     loc_180003FB2
0x180004076  lea     r8, [r14+r14]
0x18000407a  cmp     r8, 2
0x18000407e  jbe     loc_180003FB2
0x180004084  add     r11, 2
0x180004088  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000408c  xor     edx, edx; Val
0x18000408e  lea     rcx, [r11+r10*2]; void *
0x180004092  call    memset_0
0x180004097  jmp     loc_180003FB2
```
