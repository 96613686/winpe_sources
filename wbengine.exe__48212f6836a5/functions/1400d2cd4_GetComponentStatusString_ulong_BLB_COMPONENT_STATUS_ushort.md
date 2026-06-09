# GetComponentStatusString(ulong,_BLB_COMPONENT_STATUS *,ushort * *)

- ea: `0x1400d2cd4`
- end: `0x1400d2ffa`
- name: `?GetComponentStatusString@@YAJKPEAU_BLB_COMPONENT_STATUS@@PEAPEAG@Z`
- size: `806`
- prototype: `__int64 __fastcall(unsigned int, struct _BLB_COMPONENT_STATUS *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400d4ff4`

## callees

- `0x14000cbcc`
- `0x14001358c`
- `0x14008863c`
- `0x1400889f0`
- `0x1400d2cd4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400d2eee`
- `ole32!CoTaskMemFree` at `0x1400d2f1d`
- `ole32!CoTaskMemFree` at `0x1400d2f32`
- `ole32!CoTaskMemFree` at `0x1400d2fa9`
- `ole32!CoTaskMemFree` at `0x1400d2fb7`
- `ole32!CoTaskMemFree` at `0x1400d2fce`
- `ole32!CoTaskMemFree` at `0x1400d2eee`
- `ole32!CoTaskMemFree` at `0x1400d2f1d`
- `ole32!CoTaskMemFree` at `0x1400d2f32`
- `ole32!CoTaskMemFree` at `0x1400d2fa9`
- `ole32!CoTaskMemFree` at `0x1400d2fb7`
- `ole32!CoTaskMemFree` at `0x1400d2fce`
- `RPCRT4!UuidToStringW` at `0x1400d2db1`
- `RPCRT4!UuidToStringW` at `0x1400d2dc7`
- `RPCRT4!UuidToStringW` at `0x1400d2db1`
- `RPCRT4!UuidToStringW` at `0x1400d2dc7`
- `RPCRT4!RpcStringFreeW` at `0x1400d2f49`
- `RPCRT4!RpcStringFreeW` at `0x1400d2fde`
- `RPCRT4!RpcStringFreeW` at `0x1400d2f49`
- `RPCRT4!RpcStringFreeW` at `0x1400d2fde`

## string_xrefs

- `0x1400d2d17`: `<ComponentStatus>`
- `0x1400d2e6e`: `<ComponentStatusItem Name="%ws" LogicalPath="%ws" Caption="%ws" AppId="%ws" WriterId="{%ws}" InstanceId="{%ws}" ConsistencyCheckResult="%d" ConsistencyCheckResultDetailed="%d"/>`
- `0x1400d2f7b`: `</ComponentStatus>`

## pseudocode

```c
__int64 __fastcall GetComponentStatusString(unsigned int a1, struct _BLB_COMPONENT_STATUS *a2, unsigned __int16 **a3)
{
  unsigned int v3; // r14d
  struct _BLB_COMPONENT_STATUS *v5; // r13
  unsigned int v6; // r15d
  unsigned __int16 *v7; // rdi
  unsigned __int16 *v8; // rsi
  int appended; // ebx
  char *v10; // r15
  const OLECHAR *v11; // r13
  const OLECHAR *v12; // rbx
  const OLECHAR *v13; // rax
  bool v14; // zf
  const OLECHAR *v15; // rax
  __int64 v16; // r11
  __int64 v17; // r10
  __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // esi
  unsigned __int64 v23; // rdx
  void *v24; // rdi
  __int64 v26; // [rsp+48h] [rbp-31h]
  __int64 v27; // [rsp+50h] [rbp-29h]
  LPVOID pv; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 *v29; // [rsp+68h] [rbp-11h] BYREF
  RPC_WSTR v30; // [rsp+70h] [rbp-9h] BYREF
  const OLECHAR *v31; // [rsp+78h] [rbp-1h]
  const OLECHAR *v32; // [rsp+80h] [rbp+7h]
  const OLECHAR *v33; // [rsp+88h] [rbp+Fh]
  RPC_WSTR StringUuid; // [rsp+F0h] [rbp+77h] BYREF
  unsigned __int16 *v37; // [rsp+F8h] [rbp+7Fh] BYREF

  v3 = 0;
  *a3 = 0;
  v5 = a2;
  v6 = a1;
  v37 = 0;
  StringUuid = 0;
  v30 = 0;
  v29 = 0;
  v7 = 0;
  pv = 0;
  v8 = 0;
  appended = BlbutilDuplicateString(L"<ComponentStatus>", (unsigned __int16 **)&pv, 0);
  if ( appended >= 0 )
  {
    while ( v3 < v6 )
    {
      v10 = (char *)v5 + 80 * v3;
      if ( v10[72] )
      {
        v11 = &String1;
        v12 = &String1;
        if ( *((_QWORD *)v10 + 5) )
          v11 = (const OLECHAR *)*((_QWORD *)v10 + 5);
        v13 = &String1;
        if ( *((_QWORD *)v10 + 4) )
          v12 = (const OLECHAR *)*((_QWORD *)v10 + 4);
        v14 = *((_QWORD *)v10 + 6) == 0;
        v33 = v12;
        if ( !v14 )
          v13 = (const OLECHAR *)*((_QWORD *)v10 + 6);
        v14 = *((_QWORD *)v10 + 7) == 0;
        v32 = v13;
        v15 = &String1;
        if ( !v14 )
          v15 = (const OLECHAR *)*((_QWORD *)v10 + 7);
        v31 = v15;
        if ( UuidToStringW((const UUID *)v10, &StringUuid) || UuidToStringW((const UUID *)v10 + 1, &v30) )
        {
          appended = -2147467259;
          goto LABEL_46;
        }
        v16 = -1;
        do
          ++v16;
        while ( StringUuid[v16] );
        v17 = -1;
        do
          ++v17;
        while ( v30[v17] );
        v18 = -1;
        do
          ++v18;
        while ( v11[v18] );
        v19 = -1;
        do
          ++v19;
        while ( v12[v19] );
        v20 = -1;
        do
          ++v20;
        while ( v32[v20] );
        v21 = -1;
        do
          ++v21;
        while ( v31[v21] );
        v22 = v18 + 227 + v19 + v20 + v21 + v16 + v17;
        appended = BlbutilMemalloc((void **)&v29, v22, 2u);
        if ( appended < 0 )
        {
          v8 = v29;
          goto LABEL_46;
        }
        LODWORD(v27) = *((_DWORD *)v10 + 17);
        LODWORD(v26) = *((_DWORD *)v10 + 16);
        v23 = v22;
        v8 = v29;
        appended = StringCchPrintfW(
                     v29,
                     v23,
                     L"<ComponentStatusItem Name=\"%ws\" LogicalPath=\"%ws\" Caption=\"%ws\" AppId=\"%ws\" WriterId=\"{%ws"
                      "}\" InstanceId=\"{%ws}\" ConsistencyCheckResult=\"%d\" ConsistencyCheckResultDetailed=\"%d\"/>",
                     v33,
                     v11,
                     v32,
                     v31,
                     StringUuid,
                     v30,
                     v26,
                     v27);
        if ( appended < 0 )
          goto LABEL_46;
        v24 = pv;
        appended = BlbutilAppendString((const unsigned __int16 *)pv, v8, &v37);
        if ( appended < 0 )
          goto LABEL_45;
        if ( v24 )
        {
          CoTaskMemFree(v24);
          pv = 0;
        }
        v7 = v37;
        appended = BlbutilDuplicateString(v37, (unsigned __int16 **)&pv, 0);
        if ( appended < 0 )
          goto LABEL_46;
        if ( v7 )
        {
          CoTaskMemFree(v7);
          v7 = 0;
          v37 = 0;
        }
        if ( v8 )
        {
          CoTaskMemFree(v8);
          v8 = 0;
          v29 = 0;
        }
        if ( StringUuid )
        {
          RpcStringFreeW(&StringUuid);
          StringUuid = 0;
        }
        v5 = a2;
      }
      v6 = a1;
      ++v3;
    }
    appended = BlbutilAppendString((const unsigned __int16 *)pv, L"</ComponentStatus>", &v37);
    if ( appended >= 0 )
    {
      v7 = 0;
      *a3 = v37;
      goto LABEL_46;
    }
LABEL_45:
    v7 = v37;
LABEL_46:
    if ( v7 )
      CoTaskMemFree(v7);
    if ( v8 )
      CoTaskMemFree(v8);
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400d2cd4  mov     [rsp-8+arg_8], rdx
0x1400d2cd9  mov     [rsp-8+arg_0], ecx
0x1400d2cdd  push    rbp
0x1400d2cde  push    rbx
0x1400d2cdf  push    rsi
0x1400d2ce0  push    rdi
0x1400d2ce1  push    r12
0x1400d2ce3  push    r13
0x1400d2ce5  push    r14
0x1400d2ce7  push    r15
0x1400d2ce9  lea     rbp, [rsp-1Fh]
0x1400d2cee  sub     rsp, 98h
0x1400d2cf5  xor     r14d, r14d
0x1400d2cf8  mov     r12, r8
0x1400d2cfb  mov     [r8], r14
0x1400d2cfe  mov     r13, rdx
0x1400d2d01  mov     r15d, ecx
0x1400d2d04  mov     [rbp+57h+arg_18], r14
0x1400d2d08  xor     r8d, r8d; unsigned __int64
0x1400d2d0b  mov     [rbp+57h+StringUuid], r14
0x1400d2d0f  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x1400d2d13  mov     [rbp+57h+var_60], r14
0x1400d2d17  lea     rcx, aComponentstatu_0; "<ComponentStatus>"
0x1400d2d1e  mov     [rbp+57h+var_68], r14
0x1400d2d22  mov     edi, r14d
0x1400d2d25  mov     [rbp+57h+pv], r14
0x1400d2d29  mov     esi, r14d
0x1400d2d2c  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400d2d31  mov     ebx, eax
0x1400d2d33  test    eax, eax
0x1400d2d35  js      loc_1400D2FBF
0x1400d2d3b  cmp     r14d, r15d
0x1400d2d3e  jnb     loc_1400D2F73
0x1400d2d44  mov     eax, r14d
0x1400d2d47  xor     ecx, ecx
0x1400d2d49  lea     r15, [rax+rax*4]
0x1400d2d4d  shl     r15, 4
0x1400d2d51  add     r15, r13
0x1400d2d54  cmp     [r15+48h], cl
0x1400d2d58  jz      loc_1400D2F57
0x1400d2d5e  cmp     [r15+28h], rcx
0x1400d2d62  lea     r13, String1
0x1400d2d69  lea     rbx, String1
0x1400d2d70  cmovnz  r13, [r15+28h]
0x1400d2d75  lea     rax, String1
0x1400d2d7c  cmp     [r15+20h], rcx
0x1400d2d80  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x1400d2d84  cmovnz  rbx, [r15+20h]
0x1400d2d89  cmp     [r15+30h], rcx
0x1400d2d8d  mov     [rbp+57h+var_48], rbx
0x1400d2d91  cmovnz  rax, [r15+30h]
0x1400d2d96  cmp     [r15+38h], rcx
0x1400d2d9a  mov     rcx, r15; Uuid
0x1400d2d9d  mov     [rbp+57h+var_50], rax
0x1400d2da1  lea     rax, String1
0x1400d2da8  cmovnz  rax, [r15+38h]
0x1400d2dad  mov     [rbp+57h+var_58], rax
0x1400d2db1  call    cs:__imp_UuidToStringW
0x1400d2db7  test    eax, eax
0x1400d2db9  jnz     loc_1400D2F69
0x1400d2dbf  lea     rcx, [r15+10h]; Uuid
0x1400d2dc3  lea     rdx, [rbp+57h+var_60]; StringUuid
0x1400d2dc7  call    cs:__imp_UuidToStringW
0x1400d2dcd  xor     ecx, ecx
0x1400d2dcf  test    eax, eax
0x1400d2dd1  jnz     loc_1400D2F69
0x1400d2dd7  mov     rax, [rbp+57h+StringUuid]
0x1400d2ddb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400d2ddf  mov     r11, rsi
0x1400d2de2  inc     r11
0x1400d2de5  cmp     [rax+r11*2], cx
0x1400d2dea  jnz     short loc_1400D2DE2
0x1400d2dec  mov     rax, [rbp+57h+var_60]
0x1400d2df0  mov     r10, rsi
0x1400d2df3  inc     r10
0x1400d2df6  cmp     [rax+r10*2], cx
0x1400d2dfb  jnz     short loc_1400D2DF3
0x1400d2dfd  mov     r9, rsi
0x1400d2e00  inc     r9
0x1400d2e03  cmp     [r13+r9*2+0], cx
0x1400d2e09  jnz     short loc_1400D2E00
0x1400d2e0b  mov     r8, rsi
0x1400d2e0e  inc     r8
0x1400d2e11  cmp     [rbx+r8*2], cx
0x1400d2e16  jnz     short loc_1400D2E0E
0x1400d2e18  mov     rax, [rbp+57h+var_50]
0x1400d2e1c  mov     rdx, rsi
0x1400d2e1f  inc     rdx
0x1400d2e22  cmp     [rax+rdx*2], cx
0x1400d2e26  jnz     short loc_1400D2E1F
0x1400d2e28  mov     rax, [rbp+57h+var_58]
0x1400d2e2c  mov     rcx, rsi
0x1400d2e2f  xor     ebx, ebx
0x1400d2e31  inc     rcx
0x1400d2e34  cmp     [rax+rcx*2], bx
0x1400d2e38  jnz     short loc_1400D2E31
0x1400d2e3a  lea     esi, [r11+r10]
0x1400d2e3e  add     r9d, 0E3h
0x1400d2e45  add     esi, ecx
0x1400d2e47  lea     rcx, [rbp+57h+var_68]; void **
0x1400d2e4b  add     esi, edx
0x1400d2e4d  add     esi, r8d
0x1400d2e50  mov     r8d, 2; unsigned int
0x1400d2e56  add     esi, r9d
0x1400d2e59  mov     edx, esi; unsigned int
0x1400d2e5b  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400d2e60  mov     ebx, eax
0x1400d2e62  test    eax, eax
0x1400d2e64  js      loc_1400D2F63
0x1400d2e6a  mov     eax, [r15+44h]
0x1400d2e6e  lea     r8, aComponentstatu; "<ComponentStatusItem Name=\"%ws\" Logic"...
0x1400d2e75  mov     r9, [rbp+57h+var_48]
0x1400d2e79  mov     [rsp+0D0h+var_80], eax
0x1400d2e7d  mov     eax, [r15+40h]
0x1400d2e81  mov     dword ptr [rsp+0D0h+var_88], eax
0x1400d2e85  mov     rax, [rbp+57h+var_60]
0x1400d2e89  mov     [rsp+0D0h+var_90], rax
0x1400d2e8e  mov     rax, [rbp+57h+StringUuid]
0x1400d2e92  mov     [rsp+0D0h+var_98], rax
0x1400d2e97  mov     rax, [rbp+57h+var_58]
0x1400d2e9b  mov     [rsp+0D0h+var_A0], rax
0x1400d2ea0  mov     rax, [rbp+57h+var_50]
0x1400d2ea4  mov     edx, esi; unsigned __int64
0x1400d2ea6  mov     rsi, [rbp+57h+var_68]
0x1400d2eaa  mov     [rsp+0D0h+var_A8], rax
0x1400d2eaf  mov     rcx, rsi; unsigned __int16 *
0x1400d2eb2  mov     [rsp+0D0h+var_B0], r13
0x1400d2eb7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400d2ebc  xor     r15d, r15d
0x1400d2ebf  mov     ebx, eax
0x1400d2ec1  test    eax, eax
0x1400d2ec3  js      loc_1400D2FA1
0x1400d2ec9  mov     rdi, [rbp+57h+pv]
0x1400d2ecd  lea     r8, [rbp+57h+arg_18]; unsigned __int16 **
0x1400d2ed1  mov     rcx, rdi; unsigned __int16 *
0x1400d2ed4  mov     rdx, rsi; unsigned __int16 *
0x1400d2ed7  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1400d2edc  mov     ebx, eax
0x1400d2ede  test    eax, eax
0x1400d2ee0  js      loc_1400D2F9D
0x1400d2ee6  test    rdi, rdi
0x1400d2ee9  jz      short loc_1400D2EF8
0x1400d2eeb  mov     rcx, rdi; pv
0x1400d2eee  call    cs:__imp_CoTaskMemFree
0x1400d2ef4  mov     [rbp+57h+pv], r15
0x1400d2ef8  mov     rdi, [rbp+57h+arg_18]
0x1400d2efc  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x1400d2f00  mov     rcx, rdi; unsigned __int16 *
0x1400d2f03  xor     r8d, r8d; unsigned __int64
0x1400d2f06  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400d2f0b  mov     ebx, eax
0x1400d2f0d  test    eax, eax
0x1400d2f0f  js      loc_1400D2FA1
0x1400d2f15  test    rdi, rdi
0x1400d2f18  jz      short loc_1400D2F2A
0x1400d2f1a  mov     rcx, rdi; pv
0x1400d2f1d  call    cs:__imp_CoTaskMemFree
0x1400d2f23  mov     rdi, r15
0x1400d2f26  mov     [rbp+57h+arg_18], r15
0x1400d2f2a  test    rsi, rsi
0x1400d2f2d  jz      short loc_1400D2F3F
0x1400d2f2f  mov     rcx, rsi; pv
0x1400d2f32  call    cs:__imp_CoTaskMemFree
0x1400d2f38  mov     rsi, r15
0x1400d2f3b  mov     [rbp+57h+var_68], r15
0x1400d2f3f  cmp     [rbp+57h+StringUuid], r15
0x1400d2f43  jz      short loc_1400D2F53
0x1400d2f45  lea     rcx, [rbp+57h+StringUuid]; String
0x1400d2f49  call    cs:__imp_RpcStringFreeW
0x1400d2f4f  mov     [rbp+57h+StringUuid], r15
0x1400d2f53  mov     r13, [rbp+57h+arg_8]
0x1400d2f57  mov     r15d, [rbp+57h+arg_0]
0x1400d2f5b  inc     r14d
0x1400d2f5e  jmp     loc_1400D2D3B
0x1400d2f63  mov     rsi, [rbp+57h+var_68]
0x1400d2f67  jmp     short loc_1400D2F6E
0x1400d2f69  mov     ebx, 80004005h
0x1400d2f6e  xor     r15d, r15d
0x1400d2f71  jmp     short loc_1400D2FA1
0x1400d2f73  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x1400d2f77  lea     r8, [rbp+57h+arg_18]; unsigned __int16 **
0x1400d2f7b  lea     rdx, aComponentstatu_1; "</ComponentStatus>"
0x1400d2f82  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1400d2f87  xor     r15d, r15d
0x1400d2f8a  mov     ebx, eax
0x1400d2f8c  test    eax, eax
0x1400d2f8e  js      short loc_1400D2F9D
0x1400d2f90  mov     rax, [rbp+57h+arg_18]
0x1400d2f94  mov     edi, r15d
0x1400d2f97  mov     [r12], rax
0x1400d2f9b  jmp     short loc_1400D2FA1
0x1400d2f9d  mov     rdi, [rbp+57h+arg_18]
0x1400d2fa1  test    rdi, rdi
0x1400d2fa4  jz      short loc_1400D2FAF
0x1400d2fa6  mov     rcx, rdi; pv
0x1400d2fa9  call    cs:__imp_CoTaskMemFree
0x1400d2faf  test    rsi, rsi
0x1400d2fb2  jz      short loc_1400D2FC2
0x1400d2fb4  mov     rcx, rsi; pv
0x1400d2fb7  call    cs:__imp_CoTaskMemFree
0x1400d2fbd  jmp     short loc_1400D2FC2
0x1400d2fbf  xor     r15d, r15d
0x1400d2fc2  mov     rdi, [rbp+57h+pv]
0x1400d2fc6  test    rdi, rdi
0x1400d2fc9  jz      short loc_1400D2FD4
0x1400d2fcb  mov     rcx, rdi; pv
0x1400d2fce  call    cs:__imp_CoTaskMemFree
0x1400d2fd4  cmp     [rbp+57h+StringUuid], r15
0x1400d2fd8  jz      short loc_1400D2FE4
0x1400d2fda  lea     rcx, [rbp+57h+StringUuid]; String
0x1400d2fde  call    cs:__imp_RpcStringFreeW
0x1400d2fe4  mov     eax, ebx
0x1400d2fe6  add     rsp, 98h
0x1400d2fed  pop     r15
0x1400d2fef  pop     r14
0x1400d2ff1  pop     r13
0x1400d2ff3  pop     r12
0x1400d2ff5  pop     rdi
0x1400d2ff6  pop     rsi
0x1400d2ff7  pop     rbx
0x1400d2ff8  pop     rbp
0x1400d2ff9  retn
```
