# GetUserSid(HKEY__ * const,ushort const *,uchar * *)

- ea: `0x18001a18c`
- end: `0x18001a2c6`
- name: `?GetUserSid@@YAJQEAUHKEY__@@PEBGPEAPEAE@Z`
- size: `314`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800190bc`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001a18c`
- `0x18001ace4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a29d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a29d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a233`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a233`

## string_xrefs

- `0x18001a1aa`: `GetUserSid`

## pseudocode

```c
__int64 __fastcall GetUserSid(HKEY hKey, LPCWSTR lpSubKey, unsigned __int8 **a3)
{
  __int16 v6; // ax
  signed int v7; // ebx
  LSTATUS v8; // eax
  const unsigned __int16 *v9; // rdx
  __int16 v10; // ax
  int phkResult; // [rsp+20h] [rbp-50h]
  int v13; // [rsp+30h] [rbp-40h] BYREF
  __int16 v14; // [rsp+34h] [rbp-3Ch]
  __int16 v15; // [rsp+36h] [rbp-3Ah]
  unsigned int v16; // [rsp+90h] [rbp+20h] BYREF
  HKEY hKeya; // [rsp+A0h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "GetUserSid", 90, 1);
  hKeya = 0;
  v16 = 0;
  if ( a3 )
    *a3 = 0;
  v6 = 97;
  if ( hKey && (v14 = 97, v6 = 98, lpSubKey) && (v14 = 98, v6 = 99, a3) )
  {
    v14 = 99;
    v13 = 0;
    v8 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    v13 = v7;
    v10 = 102;
    if ( v7 < 0 || (v14 = 102, v7 = ReadBinaryFromRegistry(hKeya, v9, a3, &v16, phkResult), v13 = v7, v10 = 103, v7 < 0) )
    {
      v15 = v10;
    }
    else
    {
      v14 = 103;
      if ( v7 == 1 )
      {
        v13 = 1;
        v14 = 106;
      }
    }
    if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKeya);
      hKeya = 0;
    }
  }
  else
  {
    v7 = -2147024809;
    v15 = v6;
    v13 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a18c  mov     [rsp-18h+arg_8], rbx
0x18001a191  push    rbp
0x18001a192  push    rsi
0x18001a193  push    rdi
0x18001a194  mov     rbp, rsp
0x18001a197  sub     rsp, 70h
0x18001a19b  mov     r9d, 1; unsigned __int16
0x18001a1a1  mov     rdi, r8
0x18001a1a4  mov     rsi, rdx
0x18001a1a7  mov     rbx, rcx
0x18001a1aa  lea     rdx, aGetusersid; "GetUserSid"
0x18001a1b1  lea     rcx, [rbp+var_40]; this
0x18001a1b5  lea     r8d, [r9+59h]; unsigned __int16
0x18001a1b9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001a1be  mov     [rbp+hKey], 0
0x18001a1c6  mov     [rbp+arg_0], 0
0x18001a1cd  test    rdi, rdi
0x18001a1d0  jz      short loc_18001A1D9
0x18001a1d2  mov     qword ptr [rdi], 0
0x18001a1d9  mov     eax, 61h ; 'a'
0x18001a1de  test    rbx, rbx
0x18001a1e1  jnz     short loc_18001A1F4
0x18001a1e3  mov     ebx, 80070057h
0x18001a1e8  mov     [rbp+var_3A], ax
0x18001a1ec  mov     [rbp+var_40], ebx
0x18001a1ef  jmp     loc_18001A2AB
0x18001a1f4  mov     [rbp+var_3C], ax
0x18001a1f8  mov     eax, 62h ; 'b'
0x18001a1fd  test    rsi, rsi
0x18001a200  jz      short loc_18001A1E3
0x18001a202  mov     [rbp+var_3C], ax
0x18001a206  mov     eax, 63h ; 'c'
0x18001a20b  test    rdi, rdi
0x18001a20e  jz      short loc_18001A1E3
0x18001a210  mov     [rbp+var_3C], ax
0x18001a214  mov     r9d, 20019h; samDesired
0x18001a21a  lea     rax, [rbp+hKey]
0x18001a21e  mov     [rbp+var_40], 0
0x18001a225  xor     r8d, r8d; ulOptions
0x18001a228  mov     qword ptr [rsp+70h+phkResult], rax; int
0x18001a22d  mov     rdx, rsi; lpSubKey
0x18001a230  mov     rcx, rbx; hKey
0x18001a233  call    cs:__imp_RegOpenKeyExW
0x18001a239  mov     ebx, eax
0x18001a23b  test    eax, eax
0x18001a23d  jle     short loc_18001A248
0x18001a23f  movzx   ebx, ax
0x18001a242  or      ebx, 80070000h
0x18001a248  mov     [rbp+var_40], ebx
0x18001a24b  mov     eax, 66h ; 'f'
0x18001a250  test    ebx, ebx
0x18001a252  jns     short loc_18001A25A
0x18001a254  mov     [rbp+var_3A], ax
0x18001a258  jmp     short loc_18001A28F
0x18001a25a  mov     rcx, [rbp+hKey]; hKey
0x18001a25e  lea     r9, [rbp+arg_0]; unsigned int *
0x18001a262  mov     r8, rdi; unsigned __int8 **
0x18001a265  mov     [rbp+var_3C], ax
0x18001a269  call    ?ReadBinaryFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z; ReadBinaryFromRegistry(HKEY__ *,ushort const *,uchar * *,ulong *,int)
0x18001a26e  mov     ebx, eax
0x18001a270  mov     [rbp+var_40], eax
0x18001a273  test    eax, eax
0x18001a275  mov     eax, 67h ; 'g'
0x18001a27a  js      short loc_18001A254
0x18001a27c  mov     [rbp+var_3C], ax
0x18001a280  cmp     ebx, 1
0x18001a283  jnz     short loc_18001A28F
0x18001a285  lea     eax, [rbx+69h]
0x18001a288  mov     [rbp+var_40], ebx
0x18001a28b  mov     [rbp+var_3C], ax
0x18001a28f  mov     rcx, [rbp+hKey]; hKey
0x18001a293  lea     rdx, [rcx-1]
0x18001a297  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001a29b  ja      short loc_18001A2AB
0x18001a29d  call    cs:__imp_RegCloseKey
0x18001a2a3  mov     [rbp+hKey], 0
0x18001a2ab  lea     rcx, [rbp+var_40]; this
0x18001a2af  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001a2b4  mov     eax, ebx
0x18001a2b6  mov     rbx, [rsp+70h+arg_8]
0x18001a2be  add     rsp, 70h
0x18001a2c2  pop     rdi
0x18001a2c3  pop     rsi
0x18001a2c4  pop     rbp
0x18001a2c5  retn
```
