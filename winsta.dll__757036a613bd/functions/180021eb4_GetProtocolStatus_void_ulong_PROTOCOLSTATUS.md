# GetProtocolStatus(void *,ulong,_PROTOCOLSTATUS *)

- ea: `0x180021eb4`
- end: `0x1800220eb`
- name: `?GetProtocolStatus@@YAJPEAXKPEAU_PROTOCOLSTATUS@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _PROTOCOLSTATUS *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800067b0`
- `0x18000ad50`

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180021eb4`
- `0x18002fe06`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ef9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800220cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800220cb`
- `RPCRT4!NdrClientCall3` at `0x180021f70`
- `RPCRT4!NdrClientCall3` at `0x180021f70`

## string_xrefs

- `0x180021f99`: `RpcGetProtocolStatus failed: 0x%x`
- `0x180021fe7`: `RpcGetProtocolStatus returned %d bytes, expected %d`
- `0x180021f17`: `Invoke RpcGetProtocolStatus`

## pseudocode

```c
__int64 __fastcall GetProtocolStatus(void *a1, int a2, struct _PROTOCOLSTATUS *a3)
{
  signed int LastError; // eax
  CLIENT_CALL_RETURN v6; // rbx
  __int64 v7; // rax
  _OWORD *v8; // rax
  __int64 v9; // rcx
  HLOCAL hMem; // [rsp+48h] [rbp-30h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+50h] [rbp-28h]
  unsigned __int16 v13[16]; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+20h] BYREF

  hMem = 0;
  v14 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v13, a1, 1);
  if ( CSmartPublicBinding::operator void *(v13) )
  {
    _DbgPrintMessage(1, "Invoke RpcGetProtocolStatus");
    v7 = CSmartPublicBinding::operator void *(v13);
    v12.Simple = 0;
    v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0, 2u, 0, v7, a2, 0, &hMem, &v14).Pointer;
    v12.Pointer = v6.Pointer;
    if ( SLODWORD(v6.Simple) < 0 )
    {
      if ( LODWORD(v6.Pointer) == -2147022646
        || LODWORD(v6.Pointer) == -2147023174
        || LODWORD(v6.Pointer) == -2147023179 )
      {
        memset_0(a3, 0, 0x3F4u);
        LODWORD(v6.Pointer) = 0;
      }
    }
    else if ( hMem )
    {
      if ( v14 >= 0x3F4 )
      {
        v8 = hMem;
        v9 = 7;
        do
        {
          *(_OWORD *)a3 = *v8;
          *((_OWORD *)a3 + 1) = v8[1];
          *((_OWORD *)a3 + 2) = v8[2];
          *((_OWORD *)a3 + 3) = v8[3];
          *((_OWORD *)a3 + 4) = v8[4];
          *((_OWORD *)a3 + 5) = v8[5];
          *((_OWORD *)a3 + 6) = v8[6];
          *((_OWORD *)a3 + 7) = v8[7];
          a3 = (struct _PROTOCOLSTATUS *)((char *)a3 + 128);
          v8 += 8;
          --v9;
        }
        while ( v9 );
        *(_OWORD *)a3 = *v8;
        *((_OWORD *)a3 + 1) = v8[1];
        *((_OWORD *)a3 + 2) = v8[2];
        *((_OWORD *)a3 + 3) = v8[3];
        *((_OWORD *)a3 + 4) = v8[4];
        *((_OWORD *)a3 + 5) = v8[5];
        *((_OWORD *)a3 + 6) = v8[6];
        *((_DWORD *)a3 + 28) = *((_DWORD *)v8 + 28);
      }
      else
      {
        _DbgPrintMessage(8, "RpcGetProtocolStatus returned %d bytes, expected %d", v14, 1012);
        LODWORD(v6.Pointer) = -2147024809;
      }
    }
    else
    {
      LODWORD(v6.Pointer) = -2147467261;
    }
  }
  else
  {
    LastError = GetLastError();
    LODWORD(v6.Pointer) = LastError;
    if ( LastError > 0 )
      LODWORD(v6.Pointer) = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hMem )
    LocalFree(hMem);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v13);
  return LODWORD(v6.Pointer);
}

```

## disassembly

```asm
0x180021eb4  mov     rax, rsp
0x180021eb7  mov     [rax+8], rbx
0x180021ebb  mov     [rax+18h], r8
0x180021ebf  push    rdi
0x180021ec0  sub     rsp, 70h
0x180021ec4  mov     rdi, r8
0x180021ec7  mov     ebx, edx
0x180021ec9  mov     qword ptr [rax-30h], 0
0x180021ed1  mov     dword ptr [rax+20h], 0
0x180021ed8  mov     r8d, 1; int
0x180021ede  mov     rdx, rcx; void *
0x180021ee1  lea     rcx, [rax-20h]; this
0x180021ee5  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180021eea  lea     rcx, [rsp+78h+var_20]; unsigned __int16 *
0x180021eef  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021ef4  test    rax, rax
0x180021ef7  jnz     short loc_180021F17
0x180021ef9  call    cs:__imp_GetLastError
0x180021eff  mov     ebx, eax
0x180021f01  test    eax, eax
0x180021f03  jle     loc_1800220C1
0x180021f09  movzx   ebx, ax
0x180021f0c  or      ebx, 80070000h
0x180021f12  jmp     loc_1800220C1
0x180021f17  lea     rdx, aInvokeRpcgetpr; "Invoke RpcGetProtocolStatus"
0x180021f1e  mov     ecx, 1; int
0x180021f23  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021f28  nop
0x180021f29  lea     rcx, [rsp+78h+var_20]; unsigned __int16 *
0x180021f2e  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021f33  mov     [rsp+78h+var_28], 0
0x180021f3c  lea     rcx, [rsp+78h+arg_18]
0x180021f44  mov     [rsp+78h+var_40], rcx
0x180021f49  lea     rcx, [rsp+78h+hMem]
0x180021f4e  mov     [rsp+78h+var_48], rcx
0x180021f53  mov     [rsp+78h+var_50], 0
0x180021f5b  mov     [rsp+78h+var_58], ebx
0x180021f5f  mov     r9, rax
0x180021f62  xor     r8d, r8d; pReturnValue
0x180021f65  lea     edx, [r8+2]; nProcNum
0x180021f69  lea     rcx, stru_1800320E0; pProxyInfo
0x180021f70  call    cs:__imp_NdrClientCall3
0x180021f76  mov     rbx, rax
0x180021f79  mov     [rsp+78h+var_28], rax
0x180021f7e  mov     [rsp+78h+var_38], eax
0x180021f82  jmp     short loc_180021FB2
0x180021f84  test    eax, eax
0x180021f86  jle     short loc_180021F90
0x180021f88  movzx   eax, ax
0x180021f8b  or      eax, 80070000h
0x180021f90  mov     ebx, eax
0x180021f92  mov     [rsp+78h+var_38], eax
0x180021f96  mov     r8d, eax
0x180021f99  lea     rdx, aRpcgetprotocol_0; "RpcGetProtocolStatus failed: 0x%x"
0x180021fa0  mov     ecx, 8; int
0x180021fa5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021faa  mov     rdi, [rsp+78h+arg_10]
0x180021fb2  test    ebx, ebx
0x180021fb4  js      loc_180022097
0x180021fba  cmp     [rsp+78h+hMem], 0
0x180021fc0  jnz     short loc_180021FCC
0x180021fc2  mov     ebx, 80004003h
0x180021fc7  jmp     loc_1800220C1
0x180021fcc  mov     r8d, 3F4h
0x180021fd2  cmp     [rsp+78h+arg_18], r8d
0x180021fda  jnb     short loc_180022002
0x180021fdc  mov     r9d, r8d
0x180021fdf  mov     r8d, [rsp+78h+arg_18]
0x180021fe7  lea     rdx, aRpcgetprotocol; "RpcGetProtocolStatus returned %d bytes,"...
0x180021fee  mov     ecx, 8; int
0x180021ff3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021ff8  mov     ebx, 80070057h
0x180021ffd  jmp     loc_1800220C1
0x180022002  mov     rax, [rsp+78h+hMem]
0x180022007  mov     ecx, 7
0x18002200c  lea     edx, [rcx+79h]
0x18002200f  movups  xmm0, xmmword ptr [rax]
0x180022012  movups  xmmword ptr [rdi], xmm0
0x180022015  movups  xmm1, xmmword ptr [rax+10h]
0x180022019  movups  xmmword ptr [rdi+10h], xmm1
0x18002201d  movups  xmm0, xmmword ptr [rax+20h]
0x180022021  movups  xmmword ptr [rdi+20h], xmm0
0x180022025  movups  xmm1, xmmword ptr [rax+30h]
0x180022029  movups  xmmword ptr [rdi+30h], xmm1
0x18002202d  movups  xmm0, xmmword ptr [rax+40h]
0x180022031  movups  xmmword ptr [rdi+40h], xmm0
0x180022035  movups  xmm1, xmmword ptr [rax+50h]
0x180022039  movups  xmmword ptr [rdi+50h], xmm1
0x18002203d  movups  xmm0, xmmword ptr [rax+60h]
0x180022041  movups  xmmword ptr [rdi+60h], xmm0
0x180022045  movups  xmm1, xmmword ptr [rax+70h]
0x180022049  movups  xmmword ptr [rdi+70h], xmm1
0x18002204d  add     rdi, rdx
0x180022050  add     rax, rdx
0x180022053  sub     rcx, 1
0x180022057  jnz     short loc_18002200F
0x180022059  movups  xmm0, xmmword ptr [rax]
0x18002205c  movups  xmmword ptr [rdi], xmm0
0x18002205f  movups  xmm1, xmmword ptr [rax+10h]
0x180022063  movups  xmmword ptr [rdi+10h], xmm1
0x180022067  movups  xmm0, xmmword ptr [rax+20h]
0x18002206b  movups  xmmword ptr [rdi+20h], xmm0
0x18002206f  movups  xmm1, xmmword ptr [rax+30h]
0x180022073  movups  xmmword ptr [rdi+30h], xmm1
0x180022077  movups  xmm0, xmmword ptr [rax+40h]
0x18002207b  movups  xmmword ptr [rdi+40h], xmm0
0x18002207f  movups  xmm1, xmmword ptr [rax+50h]
0x180022083  movups  xmmword ptr [rdi+50h], xmm1
0x180022087  movups  xmm0, xmmword ptr [rax+60h]
0x18002208b  movups  xmmword ptr [rdi+60h], xmm0
0x18002208f  mov     eax, [rax+70h]
0x180022092  mov     [rdi+70h], eax
0x180022095  jmp     short loc_1800220C1
0x180022097  cmp     ebx, 800708CAh
0x18002209d  jz      short loc_1800220AF
0x18002209f  cmp     ebx, 800706BAh
0x1800220a5  jz      short loc_1800220AF
0x1800220a7  cmp     ebx, 800706B5h
0x1800220ad  jnz     short loc_1800220C1
0x1800220af  xor     edx, edx; Val
0x1800220b1  mov     r8d, 3F4h; Size
0x1800220b7  mov     rcx, rdi; void *
0x1800220ba  call    memset_0
0x1800220bf  xor     ebx, ebx
0x1800220c1  mov     rcx, [rsp+78h+hMem]; hMem
0x1800220c6  test    rcx, rcx
0x1800220c9  jz      short loc_1800220D1
0x1800220cb  call    cs:__imp_LocalFree
0x1800220d1  lea     rcx, [rsp+78h+var_20]; this
0x1800220d6  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800220db  mov     eax, ebx
0x1800220dd  mov     rbx, [rsp+78h+arg_0]
0x1800220e5  add     rsp, 70h
0x1800220e9  pop     rdi
0x1800220ea  retn
0x180030873  push    rbp
0x180030875  sub     rsp, 40h
0x180030879  mov     rbp, rdx
0x18003087c  mov     rcx, [rcx]
0x18003087f  mov     ecx, [rcx]; ExceptionCode
0x180030881  call    cs:__imp_I_RpcExceptionFilter
0x180030887  nop
0x180030888  add     rsp, 40h
0x18003088c  pop     rbp
0x18003088d  retn
```
