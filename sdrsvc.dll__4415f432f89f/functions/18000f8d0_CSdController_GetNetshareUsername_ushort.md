# CSdController::GetNetshareUsername(ushort * *)

- ea: `0x18000f8d0`
- end: `0x18000f9be`
- name: `?GetNetshareUsername@CSdController@@UEAAJPEAPEAG@Z`
- size: `238`
- prototype: `__int64 __fastcall(CSdController *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000f8d0`
- `0x18001586c`
- `0x180015974`
- `0x18001b0e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f98c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f99a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f98c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f99a`

## pseudocode

```c
__int64 __fastcall CSdController::GetNetshareUsername(CSdController *this, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rcx
  void *v4; // rbx
  int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rcx
  _BYTE *i; // rax
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-40h] BYREF
  __int16 v12; // [rsp+24h] [rbp-3Ch]
  __int16 v13; // [rsp+26h] [rbp-3Ah]
  LPVOID pv; // [rsp+88h] [rbp+28h] BYREF
  unsigned __int16 *v15; // [rsp+90h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "CSdController::GetNetshareUsername", 3319, 1);
  v3 = 0;
  v4 = 0;
  v15 = 0;
  pv = 0;
  if ( a2 )
  {
    *a2 = 0;
    v11 = 0;
    v12 = 3326;
    v5 = ReadCredsFromRegistry(&v15, (unsigned __int16 **)&pv);
    v4 = pv;
    if ( v5 >= 0 )
    {
      v6 = -1;
      do
        ++v6;
      while ( *((_WORD *)pv + v6) );
      v7 = 2 * v6;
      for ( i = pv; v7; --v7 )
        *i++ = 0;
      v3 = 0;
      *a2 = v15;
    }
    else
    {
      v3 = v15;
      v12 = 3331;
      v11 = 1;
    }
  }
  else
  {
    v11 = -2147024809;
    v13 = 3326;
  }
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v4 )
    CoTaskMemFree(v4);
  v9 = v11;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return v9;
}

```

## disassembly

```asm
0x18000f8d0  mov     [rsp-18h+arg_0], rbx
0x18000f8d5  push    rbp
0x18000f8d6  push    rsi
0x18000f8d7  push    rdi
0x18000f8d8  mov     rbp, rsp
0x18000f8db  sub     rsp, 60h
0x18000f8df  mov     rdi, rdx
0x18000f8e2  lea     rcx, [rbp+var_40]; this
0x18000f8e6  lea     rdx, aCsdcontrollerG_1; "CSdController::GetNetshareUsername"
0x18000f8ed  mov     r9d, 1; unsigned __int16
0x18000f8f3  mov     r8d, 0CF7h; unsigned __int16
0x18000f8f9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000f8fe  xor     esi, esi
0x18000f900  mov     eax, 0CFEh
0x18000f905  mov     ecx, esi; pv
0x18000f907  mov     ebx, esi
0x18000f909  mov     [rbp+arg_10], rcx
0x18000f90d  mov     [rbp+pv], rbx
0x18000f911  test    rdi, rdi
0x18000f914  jz      short loc_18000F97C
0x18000f916  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18000f91a  mov     [rdi], rsi
0x18000f91d  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x18000f921  mov     [rbp+var_40], esi
0x18000f924  mov     [rbp+var_3C], ax
0x18000f928  call    ?ReadCredsFromRegistry@@YAJPEAPEAG0@Z; ReadCredsFromRegistry(ushort * *,ushort * *)
0x18000f92d  mov     rbx, [rbp+pv]
0x18000f931  test    eax, eax
0x18000f933  jns     short loc_18000F94B
0x18000f935  mov     rcx, [rbp+arg_10]
0x18000f939  mov     eax, 0D03h
0x18000f93e  mov     [rbp+var_3C], ax
0x18000f942  mov     [rbp+var_40], 1
0x18000f949  jmp     short loc_18000F987
0x18000f94b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f94f  inc     rax
0x18000f952  cmp     [rbx+rax*2], si
0x18000f956  jnz     short loc_18000F94F
0x18000f958  lea     rcx, [rax+rax]
0x18000f95c  mov     rax, rbx
0x18000f95f  test    rcx, rcx
0x18000f962  jz      short loc_18000F970
0x18000f964  mov     [rax], sil
0x18000f967  inc     rax
0x18000f96a  sub     rcx, 1
0x18000f96e  jnz     short loc_18000F964
0x18000f970  mov     rax, [rbp+arg_10]
0x18000f974  mov     rcx, rsi
0x18000f977  mov     [rdi], rax
0x18000f97a  jmp     short loc_18000F987
0x18000f97c  mov     [rbp+var_40], 80070057h
0x18000f983  mov     [rbp+var_3A], ax
0x18000f987  test    rcx, rcx
0x18000f98a  jz      short loc_18000F992
0x18000f98c  call    cs:__imp_CoTaskMemFree
0x18000f992  test    rbx, rbx
0x18000f995  jz      short loc_18000F9A0
0x18000f997  mov     rcx, rbx; pv
0x18000f99a  call    cs:__imp_CoTaskMemFree
0x18000f9a0  mov     ebx, [rbp+var_40]
0x18000f9a3  lea     rcx, [rbp+var_40]; this
0x18000f9a7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000f9ac  mov     eax, ebx
0x18000f9ae  mov     rbx, [rsp+60h+arg_0]
0x18000f9b6  add     rsp, 60h
0x18000f9ba  pop     rdi
0x18000f9bb  pop     rsi
0x18000f9bc  pop     rbp
0x18000f9bd  retn
```
