# GetUserProfilePath(HKEY__ * const,ushort const *,ushort * *)

- ea: `0x180019ca0`
- end: `0x180019e52`
- name: `?GetUserProfilePath@@YAJQEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `434`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800190bc`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180019ca0`
- `0x18001b438`
- `0x18001f720`
- `0x180020488`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019d61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019d61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e01`

## string_xrefs

- `0x180019cc7`: `GetUserProfilePath`

## pseudocode

```c
__int64 __fastcall GetUserProfilePath(HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 **a3)
{
  __int16 v6; // ax
  signed int ExpandStringFromRegistry; // ebx
  LSTATUS v8; // eax
  const unsigned __int16 *v9; // rdx
  int v10; // r9d
  __int16 v11; // ax
  __int16 v12; // ax
  unsigned __int16 *v13; // rax
  __int64 *v15; // [rsp+30h] [rbp-50h] BYREF
  __int64 v16; // [rsp+38h] [rbp-48h]
  int v17; // [rsp+40h] [rbp-40h] BYREF
  __int16 v18; // [rsp+44h] [rbp-3Ch]
  __int16 v19; // [rsp+46h] [rbp-3Ah]
  HKEY hKeya; // [rsp+A0h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "GetUserProfilePath", 41, 1);
  hKeya = 0;
  v15 = qword_180028260;
  pv = 0;
  v16 = 0;
  if ( a3 )
    *a3 = 0;
  v6 = 49;
  if ( hKey )
  {
    v18 = 49;
    v6 = 50;
    if ( lpSubKey )
    {
      v18 = 50;
      v6 = 51;
      if ( a3 )
      {
        v18 = 51;
        v17 = 0;
        v8 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya);
        ExpandStringFromRegistry = v8;
        if ( v8 > 0 )
          ExpandStringFromRegistry = (unsigned __int16)v8 | 0x80070000;
        v17 = ExpandStringFromRegistry;
        v11 = 54;
        if ( ExpandStringFromRegistry >= 0 )
        {
          v18 = 54;
          ExpandStringFromRegistry = ReadExpandStringFromRegistry(hKeya, v9, (unsigned __int16 **)&pv, v10);
          v17 = ExpandStringFromRegistry;
          v11 = 55;
          if ( ExpandStringFromRegistry >= 0 )
          {
            v18 = 55;
            if ( ExpandStringFromRegistry == 1 )
            {
              v12 = 59;
LABEL_19:
              v18 = v12;
              goto LABEL_20;
            }
            v17 = CBsString::ExpandEnvironmentStringsW((CBsString *)&v15, (LPCWSTR)pv);
            ExpandStringFromRegistry = v17;
            if ( v17 >= 0 )
            {
              v13 = 0;
              v16 = 0;
              if ( v15 != qword_180028260 )
                v13 = (unsigned __int16 *)v15;
              *a3 = v13;
              v15 = qword_180028260;
              ExpandStringFromRegistry = 0;
              v12 = 69;
              goto LABEL_19;
            }
            v11 = 65;
          }
        }
        v19 = v11;
        goto LABEL_21;
      }
    }
  }
  ExpandStringFromRegistry = -2147024809;
  v19 = v6;
LABEL_20:
  v17 = ExpandStringFromRegistry;
LABEL_21:
  if ( pv )
  {
    CoTaskMemFree(pv);
    ExpandStringFromRegistry = v17;
  }
  CBsString::_Release((LPVOID *)&v15);
  if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)ExpandStringFromRegistry;
}

```

## disassembly

```asm
0x180019ca0  mov     [rsp-18h+arg_8], rbx
0x180019ca5  mov     [rsp-18h+arg_18], rsi
0x180019caa  push    rbp
0x180019cab  push    rdi
0x180019cac  push    r12
0x180019cae  mov     rbp, rsp
0x180019cb1  sub     rsp, 80h
0x180019cb8  mov     r9d, 1; unsigned __int16
0x180019cbe  mov     rdi, r8
0x180019cc1  mov     rsi, rdx
0x180019cc4  mov     rbx, rcx
0x180019cc7  lea     rdx, aGetuserprofile_0; "GetUserProfilePath"
0x180019cce  lea     rcx, [rbp+var_40]; this
0x180019cd2  lea     r8d, [r9+28h]; unsigned __int16
0x180019cd6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180019cdb  mov     [rbp+hKey], 0
0x180019ce3  lea     r12, qword_180028260
0x180019cea  mov     [rbp+var_50], r12
0x180019cee  mov     [rbp+pv], 0
0x180019cf6  mov     [rbp+var_48], 0
0x180019cfe  test    rdi, rdi
0x180019d01  jz      short loc_180019D0A
0x180019d03  mov     qword ptr [rdi], 0
0x180019d0a  mov     eax, 31h ; '1'
0x180019d0f  test    rbx, rbx
0x180019d12  jnz     short loc_180019D22
0x180019d14  mov     ebx, 80070057h
0x180019d19  mov     [rbp+var_3A], ax
0x180019d1d  jmp     loc_180019DF5
0x180019d22  mov     [rbp+var_3C], ax
0x180019d26  mov     eax, 32h ; '2'
0x180019d2b  test    rsi, rsi
0x180019d2e  jz      short loc_180019D14
0x180019d30  mov     [rbp+var_3C], ax
0x180019d34  mov     eax, 33h ; '3'
0x180019d39  test    rdi, rdi
0x180019d3c  jz      short loc_180019D14
0x180019d3e  mov     [rbp+var_3C], ax
0x180019d42  mov     r9d, 20019h; samDesired
0x180019d48  lea     rax, [rbp+hKey]
0x180019d4c  mov     [rbp+var_40], 0
0x180019d53  xor     r8d, r8d; ulOptions
0x180019d56  mov     [rsp+80h+phkResult], rax; phkResult
0x180019d5b  mov     rdx, rsi; lpSubKey
0x180019d5e  mov     rcx, rbx; hKey
0x180019d61  call    cs:__imp_RegOpenKeyExW
0x180019d67  mov     ebx, eax
0x180019d69  test    eax, eax
0x180019d6b  jle     short loc_180019D76
0x180019d6d  movzx   ebx, ax
0x180019d70  or      ebx, 80070000h
0x180019d76  mov     [rbp+var_40], ebx
0x180019d79  mov     eax, 36h ; '6'
0x180019d7e  test    ebx, ebx
0x180019d80  jns     short loc_180019D88
0x180019d82  mov     [rbp+var_3A], ax
0x180019d86  jmp     short loc_180019DF8
0x180019d88  mov     rcx, [rbp+hKey]; hKey
0x180019d8c  lea     r8, [rbp+pv]; unsigned __int16 **
0x180019d90  mov     [rbp+var_3C], ax
0x180019d94  call    ?ReadExpandStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadExpandStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180019d99  mov     ebx, eax
0x180019d9b  mov     [rbp+var_40], eax
0x180019d9e  test    eax, eax
0x180019da0  mov     eax, 37h ; '7'
0x180019da5  js      short loc_180019D82
0x180019da7  mov     [rbp+var_3C], ax
0x180019dab  cmp     ebx, 1
0x180019dae  jnz     short loc_180019DB5
0x180019db0  lea     eax, [rbx+3Ah]
0x180019db3  jmp     short loc_180019DF1
0x180019db5  mov     rdx, [rbp+pv]; lpSrc
0x180019db9  lea     rcx, [rbp+var_50]; this
0x180019dbd  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x180019dc2  mov     [rbp+var_40], eax
0x180019dc5  mov     ebx, eax
0x180019dc7  test    eax, eax
0x180019dc9  jns     short loc_180019DD2
0x180019dcb  mov     eax, 41h ; 'A'
0x180019dd0  jmp     short loc_180019D82
0x180019dd2  xor     eax, eax
0x180019dd4  mov     [rbp+var_48], 0
0x180019ddc  cmp     [rbp+var_50], r12
0x180019de0  cmovnz  rax, [rbp+var_50]
0x180019de5  mov     [rdi], rax
0x180019de8  mov     [rbp+var_50], r12
0x180019dec  xor     ebx, ebx
0x180019dee  lea     eax, [rbx+45h]
0x180019df1  mov     [rbp+var_3C], ax
0x180019df5  mov     [rbp+var_40], ebx
0x180019df8  mov     rcx, [rbp+pv]; pv
0x180019dfc  test    rcx, rcx
0x180019dff  jz      short loc_180019E0A
0x180019e01  call    cs:__imp_CoTaskMemFree
0x180019e07  mov     ebx, [rbp+var_40]
0x180019e0a  lea     rcx, [rbp+var_50]; this
0x180019e0e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180019e13  mov     rcx, [rbp+hKey]; hKey
0x180019e17  lea     rdx, [rcx-1]
0x180019e1b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180019e1f  ja      short loc_180019E2F
0x180019e21  call    cs:__imp_RegCloseKey
0x180019e27  mov     [rbp+hKey], 0
0x180019e2f  lea     rcx, [rbp+var_40]; this
0x180019e33  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180019e38  lea     r11, [rsp+80h+var_s0]
0x180019e40  mov     eax, ebx
0x180019e42  mov     rbx, [r11+28h]
0x180019e46  mov     rsi, [r11+38h]
0x180019e4a  mov     rsp, r11
0x180019e4d  pop     r12
0x180019e4f  pop     rdi
0x180019e50  pop     rbp
0x180019e51  retn
```
