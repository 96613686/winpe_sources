# CWiaItem::CopyParentReadWriteProperties(IUnknown *)

- ea: `0x18005fa70`
- end: `0x18005fd75`
- name: `?CopyParentReadWriteProperties@CWiaItem@@AEAAJPEAUIUnknown@@@Z`
- size: `773`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005fff0`

## callees

- `0x18000c7c0`
- `0x18000da10`
- `0x18000dd00`
- `0x18005fa70`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005fcf1`
- `KERNEL32!LocalFree` at `0x18005fcff`
- `KERNEL32!LocalFree` at `0x18005fcf1`
- `KERNEL32!LocalFree` at `0x18005fcff`
- `KERNEL32!LocalAlloc` at `0x18005fb6b`
- `KERNEL32!LocalAlloc` at `0x18005fb81`
- `KERNEL32!LocalAlloc` at `0x18005fb6b`
- `KERNEL32!LocalAlloc` at `0x18005fb81`
- `ole32!CoTaskMemFree` at `0x18005fc5a`
- `ole32!CoTaskMemFree` at `0x18005fc5a`
- `ole32!PropVariantClear` at `0x18005fc50`
- `ole32!PropVariantClear` at `0x18005fc50`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18005fcdc`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18005fcdc`

## string_xrefs

- `0x18005faa7`: `CWiaItem::CopyParentReadWriteProperties`
- `0x18005fad2`: `CWiaItem::CopyParentReadWriteProperties`

## pseudocode

```c
__int64 __fastcall CWiaItem::CopyParentReadWriteProperties(CWiaItem *this, struct IUnknown *a2)
{
  char ***v4; // rax
  char *v5; // rdx
  __int64 v6; // r8
  int v7; // ebx
  char *v8; // r14
  PROPVARIANT *v9; // rax
  PROPVARIANT *v10; // rsi
  ULONG v11; // edi
  __int64 v12; // rax
  bool v13; // zf
  unsigned int v15; // [rsp+20h] [rbp-79h]
  __int64 v16; // [rsp+30h] [rbp-69h] BYREF
  __int64 v17; // [rsp+38h] [rbp-61h] BYREF
  __int64 v18; // [rsp+40h] [rbp-59h] BYREF
  __int128 v19; // [rsp+48h] [rbp-51h] BYREF
  LPVOID pv[2]; // [rsp+58h] [rbp-41h] BYREF
  PROPVARIANT pvar[3]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v22[112]; // [rsp+80h] [rbp-19h] BYREF
  ULONG v23; // [rsp+108h] [rbp+6Fh] BYREF
  int v24; // [rsp+110h] [rbp+77h] BYREF
  int v25; // [rsp+118h] [rbp+7Fh] BYREF

  v16 = 0;
  v18 = 0;
  v17 = 0;
  memset(pvar, 0, sizeof(pvar));
  *(_OWORD *)pv = 0;
  LODWORD(v19) = 0;
  *((_QWORD *)&v19 + 1) = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v4 = (char ***)WiaTrace_Trace("CWiaItem::CopyParentReadWriteProperties");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v22, v5, v6, (char **)"CWiaItem::CopyParentReadWriteProperties", v15, v4);
  if ( !a2 )
  {
    v7 = -2147467261;
    goto LABEL_26;
  }
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IWiaPropertyStorage,
         &v16);
  if ( v7 >= 0 )
  {
    v7 = (**(__int64 (__fastcall ***)(CWiaItem *, GUID *, __int64 *))this)(this, &IID_IWiaPropertyStorage, &v18);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, ULONG *))(*(_QWORD *)v16 + 128LL))(v16, &v23);
      if ( v7 >= 0 )
      {
        v8 = (char *)LocalAlloc(0x40u, 16LL * v23);
        v9 = (PROPVARIANT *)LocalAlloc(0x40u, 24LL * v23);
        v10 = v9;
        if ( v8 && v9 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 88LL))(v16, &v17);
          if ( v7 >= 0 )
          {
            v11 = 0;
            if ( !v17 )
              goto LABEL_20;
            v7 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v17 + 24LL))(
                   v17,
                   1,
                   pv,
                   &v25);
            if ( !v7 )
            {
              do
              {
                DWORD2(v19) = pv[1];
                LODWORD(v19) = 1;
                memset(pvar, 0, sizeof(pvar));
                v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, int *, PROPVARIANT *))(*(_QWORD *)v16 + 120LL))(
                       v16,
                       1,
                       &v19,
                       &v24,
                       pvar);
                if ( v7 >= 0 )
                {
                  if ( (v24 & 2) != 0 && v11 < v23 )
                  {
                    v12 = 2LL * v11++;
                    *(_OWORD *)&v8[8 * v12] = v19;
                  }
                  PropVariantClear(pvar);
                }
                CoTaskMemFree(pv[0]);
                pv[0] = 0;
                v13 = v7 == 0;
                if ( v7 >= 0 )
                {
                  v7 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v17 + 24LL))(
                         v17,
                         1,
                         pv,
                         &v25);
                  v13 = v7 == 0;
                }
              }
              while ( v13 );
            }
            if ( v7 >= 0 )
            {
LABEL_20:
              v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, PROPVARIANT *))(*(_QWORD *)v18 + 24LL))(
                     v18,
                     v11,
                     v8,
                     v10);
              if ( !v7 )
              {
                v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, PROPVARIANT *, int))(*(_QWORD *)v16 + 32LL))(
                       v16,
                       v11,
                       v8,
                       v10,
                       4098);
                FreePropVariantArray(v11, v10);
              }
            }
          }
        }
        else
        {
          v7 = -2147024882;
          if ( !v8 )
            goto LABEL_24;
        }
        LocalFree(v8);
LABEL_24:
        if ( v10 )
          LocalFree(v10);
      }
    }
  }
LABEL_26:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005fa70  push    rbp
0x18005fa72  push    rbx
0x18005fa73  push    rsi
0x18005fa74  push    rdi
0x18005fa75  push    r14
0x18005fa77  lea     rbp, [rsp-37h]
0x18005fa7c  sub     rsp, 0D0h
0x18005fa83  xor     eax, eax
0x18005fa85  mov     [rbp+57h+var_C0], 0
0x18005fa8d  xorps   xmm0, xmm0
0x18005fa90  mov     [rbp+57h+var_B0], 0
0x18005fa98  mov     rdi, rcx
0x18005fa9b  mov     [rbp+57h+var_B8], 0
0x18005faa3  movups  xmmword ptr [rbp+57h+pvar+2], xmm0
0x18005faa7  lea     rcx, aCwiaitemCopypa; "CWiaItem::CopyParentReadWriteProperties"
0x18005faae  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18005fab2  mov     rbx, rdx
0x18005fab5  mov     word ptr [rbp+57h+pvar], ax
0x18005fab9  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18005fabd  mov     dword ptr [rbp+57h+var_A8], eax
0x18005fac0  mov     qword ptr [rbp+57h+var_A8+8], rax
0x18005fac4  mov     [rbp+57h+arg_18], eax
0x18005fac7  mov     [rbp+57h+arg_10], eax
0x18005faca  mov     [rbp+57h+arg_8], eax
0x18005facd  call    WiaTrace_Trace
0x18005fad2  lea     r9, aCwiaitemCopypa; "CWiaItem::CopyParentReadWriteProperties"
0x18005fad9  mov     [rsp+0F0h+var_C8], rax; struct tagWiaTraceData_Type *
0x18005fade  lea     rcx, [rbp+57h+var_70]; this
0x18005fae2  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18005fae7  test    rbx, rbx
0x18005faea  jnz     short loc_18005FAF6
0x18005faec  mov     ebx, 80004003h
0x18005faf1  jmp     loc_18005FD05
0x18005faf6  mov     rax, [rbx]
0x18005faf9  lea     r8, [rbp+57h+var_C0]
0x18005fafd  lea     rdx, IID_IWiaPropertyStorage
0x18005fb04  mov     rcx, rbx
0x18005fb07  mov     rax, [rax]
0x18005fb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb0f  mov     ebx, eax
0x18005fb11  test    eax, eax
0x18005fb13  js      loc_18005FD05
0x18005fb19  mov     rax, [rdi]
0x18005fb1c  lea     r8, [rbp+57h+var_B0]
0x18005fb20  lea     rdx, IID_IWiaPropertyStorage
0x18005fb27  mov     rcx, rdi
0x18005fb2a  mov     rax, [rax]
0x18005fb2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb32  mov     ebx, eax
0x18005fb34  test    eax, eax
0x18005fb36  js      loc_18005FD05
0x18005fb3c  mov     rcx, [rbp+57h+var_C0]
0x18005fb40  lea     rdx, [rbp+57h+arg_8]
0x18005fb44  mov     rax, [rcx]
0x18005fb47  mov     rax, [rax+80h]
0x18005fb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb53  mov     ebx, eax
0x18005fb55  test    eax, eax
0x18005fb57  js      loc_18005FD05
0x18005fb5d  mov     edx, [rbp+57h+arg_8]
0x18005fb60  mov     ebx, 40h ; '@'
0x18005fb65  shl     rdx, 4; uBytes
0x18005fb69  mov     ecx, ebx; uFlags
0x18005fb6b  call    cs:__imp_LocalAlloc
0x18005fb71  mov     edx, [rbp+57h+arg_8]
0x18005fb74  mov     ecx, ebx; uFlags
0x18005fb76  mov     r14, rax
0x18005fb79  lea     rdx, [rdx+rdx*2]
0x18005fb7d  shl     rdx, 3; uBytes
0x18005fb81  call    cs:__imp_LocalAlloc
0x18005fb87  mov     rsi, rax
0x18005fb8a  test    r14, r14
0x18005fb8d  jz      loc_18005FCE4
0x18005fb93  test    rax, rax
0x18005fb96  jz      loc_18005FCE4
0x18005fb9c  mov     rcx, [rbp+57h+var_C0]
0x18005fba0  mov     rdx, [rcx]
0x18005fba3  mov     rax, [rdx+58h]
0x18005fba7  lea     rdx, [rbp+57h+var_B8]
0x18005fbab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fbb0  mov     ebx, eax
0x18005fbb2  test    eax, eax
0x18005fbb4  js      loc_18005FCEE
0x18005fbba  mov     rcx, [rbp+57h+var_B8]
0x18005fbbe  xor     edi, edi
0x18005fbc0  test    rcx, rcx
0x18005fbc3  jz      loc_18005FC97
0x18005fbc9  mov     rax, [rcx]
0x18005fbcc  lea     r9, [rbp+57h+arg_18]
0x18005fbd0  lea     r8, [rbp+57h+pv]
0x18005fbd4  lea     edx, [rdi+1]
0x18005fbd7  mov     rax, [rax+18h]
0x18005fbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fbe0  mov     ebx, eax
0x18005fbe2  test    eax, eax
0x18005fbe4  jnz     loc_18005FC93
0x18005fbea  mov     eax, dword ptr [rbp+57h+pv+8]
0x18005fbed  lea     rdx, [rbp+57h+pvar]
0x18005fbf1  mov     rcx, [rbp+57h+var_C0]
0x18005fbf5  lea     r9, [rbp+57h+arg_10]
0x18005fbf9  mov     dword ptr [rbp+57h+var_A8+8], eax
0x18005fbfc  lea     r8, [rbp+57h+var_A8]
0x18005fc00  xor     eax, eax
0x18005fc02  mov     dword ptr [rbp+57h+var_A8], 1
0x18005fc09  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18005fc0d  xorps   xmm0, xmm0
0x18005fc10  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18005fc14  mov     rax, [rcx]
0x18005fc17  mov     [rsp+0F0h+var_D0], rdx
0x18005fc1c  mov     edx, 1
0x18005fc21  mov     rax, [rax+78h]
0x18005fc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc2a  mov     ebx, eax
0x18005fc2c  test    eax, eax
0x18005fc2e  js      short loc_18005FC56
0x18005fc30  test    byte ptr [rbp+57h+arg_10], 2
0x18005fc34  jz      short loc_18005FC4C
0x18005fc36  cmp     edi, [rbp+57h+arg_8]
0x18005fc39  jnb     short loc_18005FC4C
0x18005fc3b  movups  xmm0, [rbp+57h+var_A8]
0x18005fc3f  mov     eax, edi
0x18005fc41  add     rax, rax
0x18005fc44  inc     edi
0x18005fc46  movdqu  xmmword ptr [r14+rax*8], xmm0
0x18005fc4c  lea     rcx, [rbp+57h+pvar]; pvar
0x18005fc50  call    cs:__imp_PropVariantClear
0x18005fc56  mov     rcx, [rbp+57h+pv]; pv
0x18005fc5a  call    cs:__imp_CoTaskMemFree
0x18005fc60  mov     [rbp+57h+pv], 0
0x18005fc68  test    ebx, ebx
0x18005fc6a  js      short loc_18005FC8D
0x18005fc6c  mov     rcx, [rbp+57h+var_B8]
0x18005fc70  lea     r9, [rbp+57h+arg_18]
0x18005fc74  lea     r8, [rbp+57h+pv]
0x18005fc78  mov     edx, 1
0x18005fc7d  mov     rax, [rcx]
0x18005fc80  mov     rax, [rax+18h]
0x18005fc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc89  mov     ebx, eax
0x18005fc8b  test    eax, eax
0x18005fc8d  jz      loc_18005FBEA
0x18005fc93  test    ebx, ebx
0x18005fc95  js      short loc_18005FCEE
0x18005fc97  mov     rcx, [rbp+57h+var_B0]
0x18005fc9b  mov     r9, rsi
0x18005fc9e  mov     r8, r14
0x18005fca1  mov     edx, edi
0x18005fca3  mov     rax, [rcx]
0x18005fca6  mov     rax, [rax+18h]
0x18005fcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcaf  mov     ebx, eax
0x18005fcb1  test    eax, eax
0x18005fcb3  jnz     short loc_18005FCEE
0x18005fcb5  mov     rcx, [rbp+57h+var_C0]
0x18005fcb9  mov     r9, rsi
0x18005fcbc  mov     r8, r14
0x18005fcbf  mov     dword ptr [rsp+0F0h+var_D0], 1002h
0x18005fcc7  mov     edx, edi
0x18005fcc9  mov     rax, [rcx]
0x18005fccc  mov     rax, [rax+20h]
0x18005fcd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcd5  mov     rdx, rsi; rgvars
0x18005fcd8  mov     ecx, edi; cVariants
0x18005fcda  mov     ebx, eax
0x18005fcdc  call    cs:__imp_FreePropVariantArray
0x18005fce2  jmp     short loc_18005FCEE
0x18005fce4  mov     ebx, 8007000Eh
0x18005fce9  test    r14, r14
0x18005fcec  jz      short loc_18005FCF7
0x18005fcee  mov     rcx, r14; hMem
0x18005fcf1  call    cs:__imp_LocalFree
0x18005fcf7  test    rsi, rsi
0x18005fcfa  jz      short loc_18005FD05
0x18005fcfc  mov     rcx, rsi; hMem
0x18005fcff  call    cs:__imp_LocalFree
0x18005fd05  mov     rcx, [rbp+57h+var_B8]
0x18005fd09  test    rcx, rcx
0x18005fd0c  jz      short loc_18005FD22
0x18005fd0e  mov     rax, [rcx]
0x18005fd11  mov     rax, [rax+10h]
0x18005fd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd1a  mov     [rbp+57h+var_B8], 0
0x18005fd22  mov     rcx, [rbp+57h+var_C0]
0x18005fd26  test    rcx, rcx
0x18005fd29  jz      short loc_18005FD3F
0x18005fd2b  mov     rax, [rcx]
0x18005fd2e  mov     rax, [rax+10h]
0x18005fd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd37  mov     [rbp+57h+var_C0], 0
0x18005fd3f  mov     rcx, [rbp+57h+var_B0]
0x18005fd43  test    rcx, rcx
0x18005fd46  jz      short loc_18005FD5C
0x18005fd48  mov     rax, [rcx]
0x18005fd4b  mov     rax, [rax+10h]
0x18005fd4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd54  mov     [rbp+57h+var_B0], 0
0x18005fd5c  lea     rcx, [rbp+57h+var_70]; this
0x18005fd60  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18005fd65  mov     eax, ebx
0x18005fd67  add     rsp, 0D0h
0x18005fd6e  pop     r14
0x18005fd70  pop     rdi
0x18005fd71  pop     rsi
0x18005fd72  pop     rbx
0x18005fd73  pop     rbp
0x18005fd74  retn
```
