# WriteBinaryToRegistryEncrypted(HKEY__ *,ushort const *,uchar const *,ulong)

- ea: `0x18001b640`
- end: `0x18001b768`
- name: `?WriteBinaryToRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEBEK@Z`
- size: `296`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b770`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001b640`
- `0x18001be3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b704`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b704`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b747`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b747`

## string_xrefs

- `0x18001b662`: `WriteBinaryToRegistryEncrypted`

## pseudocode

```c
__int64 __fastcall WriteBinaryToRegistryEncrypted(HKEY hKey, LPCWSTR lpValueName, BYTE *a3, DWORD a4)
{
  __int16 v8; // ax
  signed int v9; // ebx
  int v10; // eax
  BYTE *v11; // rdi
  __int64 v12; // rsi
  bool v13; // sf
  __int16 v14; // ax
  LSTATUS v15; // eax
  __int64 v16; // rdx
  BYTE *v17; // rax
  BYTE *lpData; // [rsp+30h] [rbp-48h] BYREF
  int v20; // [rsp+38h] [rbp-40h] BYREF
  __int16 v21; // [rsp+3Ch] [rbp-3Ch]
  __int16 v22; // [rsp+3Eh] [rbp-3Ah]
  DWORD cbData; // [rsp+B8h] [rbp+40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "WriteBinaryToRegistryEncrypted", 452, 1);
  lpData = 0;
  v8 = 457;
  cbData = 0;
  if ( lpValueName && (v21 = 457, v8 = 458, a3) )
  {
    v20 = 0;
    v21 = 458;
    v10 = EncryptBlob(a3, a4, &lpData, &cbData);
    v11 = lpData;
    v9 = v10;
    v12 = cbData;
    v13 = v10 < 0;
    v20 = v10;
    v14 = 460;
    if ( v13 )
      goto LABEL_5;
    v21 = 460;
    v15 = RegSetValueExW(hKey, lpValueName, 0, 3u, lpData, cbData);
    v9 = v15;
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
    v20 = v9;
    v14 = 461;
    if ( v9 < 0 )
LABEL_5:
      v22 = v14;
    else
      v21 = 461;
    if ( v11 )
    {
      v16 = v12;
      v17 = v11;
      if ( (_DWORD)v12 )
      {
        do
        {
          *v17++ = 0;
          --v16;
        }
        while ( v16 );
      }
      CoTaskMemFree(v11);
      v9 = v20;
    }
  }
  else
  {
    v9 = -2147024809;
    v22 = v8;
    v20 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001b640  push    rbp
0x18001b642  push    rbx
0x18001b643  push    rsi
0x18001b644  push    rdi
0x18001b645  push    r14
0x18001b647  push    r15
0x18001b649  mov     rbp, rsp
0x18001b64c  sub     rsp, 78h
0x18001b650  mov     edi, r9d
0x18001b653  mov     rbx, r8
0x18001b656  mov     r14, rdx
0x18001b659  mov     r15, rcx
0x18001b65c  mov     r9d, 1; unsigned __int16
0x18001b662  lea     rdx, aWritebinarytor; "WriteBinaryToRegistryEncrypted"
0x18001b669  mov     r8d, 1C4h; unsigned __int16
0x18001b66f  lea     rcx, [rbp+var_40]; this
0x18001b673  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001b678  mov     [rbp+var_48], 0
0x18001b680  mov     eax, 1C9h
0x18001b685  mov     [rbp+arg_8], 0
0x18001b68c  test    r14, r14
0x18001b68f  jnz     short loc_18001B6A2
0x18001b691  mov     ebx, 80070057h
0x18001b696  mov     [rbp+var_3A], ax
0x18001b69a  mov     [rbp+var_40], ebx
0x18001b69d  jmp     loc_18001B750
0x18001b6a2  mov     [rbp+var_3C], ax
0x18001b6a6  mov     eax, 1CAh
0x18001b6ab  test    rbx, rbx
0x18001b6ae  jz      short loc_18001B691
0x18001b6b0  lea     r9, [rbp+arg_8]; unsigned int *
0x18001b6b4  mov     [rbp+var_40], 0
0x18001b6bb  lea     r8, [rbp+var_48]; unsigned __int8 **
0x18001b6bf  mov     [rbp+var_3C], ax
0x18001b6c3  mov     edx, edi; unsigned int
0x18001b6c5  mov     rcx, rbx; unsigned __int8 *
0x18001b6c8  call    ?EncryptBlob@@YAJPEBEKPEAPEAEPEAK@Z; EncryptBlob(uchar const *,ulong,uchar * *,ulong *)
0x18001b6cd  mov     rdi, [rbp+var_48]
0x18001b6d1  mov     ebx, eax
0x18001b6d3  mov     esi, [rbp+arg_8]
0x18001b6d6  test    eax, eax
0x18001b6d8  mov     [rbp+var_40], eax
0x18001b6db  mov     eax, 1CCh
0x18001b6e0  jns     short loc_18001B6E8
0x18001b6e2  mov     [rbp+var_3A], ax
0x18001b6e6  jmp     short loc_18001B729
0x18001b6e8  mov     [rsp+78h+cbData], esi; cbData
0x18001b6ec  mov     r9d, 3; dwType
0x18001b6f2  xor     r8d, r8d; Reserved
0x18001b6f5  mov     [rsp+78h+lpData], rdi; lpData
0x18001b6fa  mov     rdx, r14; lpValueName
0x18001b6fd  mov     [rbp+var_3C], ax
0x18001b701  mov     rcx, r15; hKey
0x18001b704  call    cs:__imp_RegSetValueExW
0x18001b70a  mov     ebx, eax
0x18001b70c  test    eax, eax
0x18001b70e  jle     short loc_18001B719
0x18001b710  movzx   ebx, ax
0x18001b713  or      ebx, 80070000h
0x18001b719  mov     [rbp+var_40], ebx
0x18001b71c  mov     eax, 1CDh
0x18001b721  test    ebx, ebx
0x18001b723  js      short loc_18001B6E2
0x18001b725  mov     [rbp+var_3C], ax
0x18001b729  test    rdi, rdi
0x18001b72c  jz      short loc_18001B750
0x18001b72e  mov     rdx, rsi
0x18001b731  mov     rax, rdi
0x18001b734  test    esi, esi
0x18001b736  jz      short loc_18001B744
0x18001b738  mov     byte ptr [rax], 0
0x18001b73b  inc     rax
0x18001b73e  sub     rdx, 1
0x18001b742  jnz     short loc_18001B738
0x18001b744  mov     rcx, rdi; pv
0x18001b747  call    cs:__imp_CoTaskMemFree
0x18001b74d  mov     ebx, [rbp+var_40]
0x18001b750  lea     rcx, [rbp+var_40]; this
0x18001b754  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001b759  mov     eax, ebx
0x18001b75b  add     rsp, 78h
0x18001b75f  pop     r15
0x18001b761  pop     r14
0x18001b763  pop     rdi
0x18001b764  pop     rsi
0x18001b765  pop     rbx
0x18001b766  pop     rbp
0x18001b767  retn
```
