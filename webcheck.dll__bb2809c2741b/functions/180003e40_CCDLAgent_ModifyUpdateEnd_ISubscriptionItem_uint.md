# CCDLAgent::ModifyUpdateEnd(ISubscriptionItem *,uint *)

- ea: `0x180003e40`
- end: `0x18000414d`
- name: `?ModifyUpdateEnd@CCDLAgent@@MEAAJPEAUISubscriptionItem@@PEAI@Z`
- size: `781`
- prototype: `int(CCDLAgent *__hidden this, struct ISubscriptionItem *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003138`
- `0x180003d20`
- `0x180003e40`
- `0x180004adc`
- `0x18001dc38`
- `0x18001dcc4`
- `0x18001dd34`
- `0x180029280`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800040a6`
- `KERNEL32!LocalAlloc` at `0x1800040a6`
- `KERNEL32!LocalFree` at `0x1800040eb`
- `KERNEL32!LocalFree` at `0x1800040eb`
- `USER32!LoadStringW` at `0x18000404b`
- `USER32!LoadStringW` at `0x18000404b`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f73`
- `OLEAUT32!__imp_SysAllocString` at `0x180003fcc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800040df`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f73`
- `OLEAUT32!__imp_SysAllocString` at `0x180003fcc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800040df`
- `OLEAUT32!__imp_SysFreeString` at `0x180003f9a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800040d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000410b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003f9a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800040d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000410b`
- `OLEAUT32!__imp_VariantInit` at `0x180003f1e`
- `OLEAUT32!__imp_VariantInit` at `0x180003f1e`
- `OLEAUT32!__imp_VariantClear` at `0x180003f61`
- `OLEAUT32!__imp_VariantClear` at `0x180003f61`

## pseudocode

```c
__int64 __fastcall CCDLAgent::ModifyUpdateEnd(CCDLAgent *this, struct ISubscriptionItem *a2, unsigned int *a3)
{
  int v3; // eax
  const unsigned __int16 *v6; // rdx
  OLECHAR *v7; // rcx
  OLECHAR *v8; // rdi
  const unsigned __int16 *v9; // rdx
  const OLECHAR *v10; // rcx
  OLECHAR *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  bool v18; // zf
  __int64 v19; // rax
  __int64 v20; // r14
  unsigned __int16 *v21; // rax
  OLECHAR *v22; // rsi
  VARIANTARG pvarg; // [rsp+30h] [rbp-678h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-658h] BYREF
  unsigned __int16 v26[520]; // [rsp+260h] [rbp-448h] BYREF

  v3 = *((_DWORD *)this + 27);
  memset(&pvarg, 0, sizeof(pvarg));
  switch ( v3 )
  {
    case -2147467259:
      goto LABEL_15;
    case -2147024882:
      *a3 = 8014;
      goto LABEL_16;
    case -2147023900:
    case -2147023673:
    case -2146762748:
    case -2146762485:
      *((_DWORD *)this + 27) = 0;
      goto LABEL_13;
    case 0:
LABEL_13:
      *a3 = 8034;
      goto LABEL_16;
    case 1:
      *a3 = 8035;
      goto LABEL_16;
  }
  if ( v3 != 790401 )
  {
LABEL_15:
    *a3 = 8033;
    goto LABEL_16;
  }
  *a3 = 8032;
LABEL_16:
  if ( *((int *)this + 27) >= 0 && *((_DWORD *)this + 27) != 1 )
    WriteDWORD(a2, L"EnableShortcutGleam", 1u);
  if ( *((_DWORD *)this + 63) )
  {
    VariantInit(&pvarg);
    WriteDWORD(a2, L"EmailFlags", 1u);
    if ( (int)GetXMLAttribute(*((struct IXMLElement **)this + 15), v6, &pvarg) >= 0 )
    {
      WriteOLESTR(a2, L"URL", pvarg.bstrVal);
      VariantClear(&pvarg);
    }
    v7 = (OLECHAR *)*((_QWORD *)this + 20);
    if ( v7 )
    {
      v8 = SysAllocString(v7);
      if ( v8 )
      {
        WriteOLESTR(a2, L"EmailTitle", *((const unsigned __int16 **)this + 20));
        SysFreeString(v8);
      }
    }
    v9 = (const unsigned __int16 *)*((unsigned int *)this + 27);
    if ( (int)v9 < 0 && !*((_QWORD *)this + 27) )
      *((_QWORD *)this + 27) = CCDLAgent::GetErrorMessage((CCDLAgent *)v7, (int)v9);
    v10 = (const OLECHAR *)*((_QWORD *)this + 21);
    if ( v10 )
    {
      v11 = SysAllocString(v10);
      if ( v11 )
      {
        v12 = *((_QWORD *)this + 27);
        if ( v12 )
        {
          v13 = -1;
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)(v12 + 2 * v14) );
          v15 = (unsigned int)(v14 - 1);
          if ( (_DWORD)v14 != 1 )
          {
            do
            {
              v16 = *((_QWORD *)this + 27);
              if ( *(_WORD *)(v16 + 2 * v15) > 0x2Eu )
                break;
              v17 = 0x400000002400LL;
              if ( !_bittest64(&v17, *(unsigned __int16 *)(v16 + 2 * v15)) )
                break;
              *(_WORD *)(v16 + 2 * v15) = 0;
              v18 = (_DWORD)v15 == 1;
              v15 = (unsigned int)(v15 - 1);
            }
            while ( !v18 );
          }
          if ( LoadStringW(g_hinstMUI, 0x1F56u, Buffer, 260) > 0 )
          {
            StringCchPrintfW(v26, 0x208u, Buffer, *((_QWORD *)this + 27));
            v19 = -1;
            do
              ++v19;
            while ( v26[v19] );
            do
              ++v13;
            while ( v11[v13] );
            v20 = (unsigned int)(v19 + v13 + 4);
            v21 = (unsigned __int16 *)LocalAlloc(0, 2 * v20);
            v22 = v21;
            if ( v21 )
            {
              StringCchPrintfW(v21, (unsigned int)v20, L"%s%ws", v26, v11);
              SysFreeString(v11);
              v11 = SysAllocString(v22);
              LocalFree(v22);
            }
          }
        }
        WriteOLESTR(a2, L"EmailAbstract", v11);
        if ( v11 )
          SysFreeString(v11);
      }
    }
    *((_DWORD *)this + 27) = 0;
    WriteSCODE(a2, v9, 0);
  }
  *((_DWORD *)this + 11) &= ~4u;
  return 0;
}

```

## disassembly

```asm
0x180003e40  mov     [rsp+arg_18], rbx
0x180003e45  push    rbp
0x180003e46  push    rsi
0x180003e47  push    rdi
0x180003e48  push    r14
0x180003e4a  push    r15
0x180003e4c  sub     rsp, 680h
0x180003e53  mov     rax, cs:__security_cookie
0x180003e5a  xor     rax, rsp
0x180003e5d  mov     [rsp+6A8h+var_38], rax
0x180003e65  xor     eax, eax
0x180003e67  xor     r15d, r15d
0x180003e6a  mov     qword ptr [rsp+6A8h+pvarg+10h], rax
0x180003e6f  xorps   xmm0, xmm0
0x180003e72  mov     eax, [rcx+6Ch]
0x180003e75  mov     rbp, rdx
0x180003e78  mov     rbx, rcx
0x180003e7b  lea     edi, [r15+1]
0x180003e7f  movups  xmmword ptr [rsp+6A8h+pvarg], xmm0
0x180003e84  cmp     eax, 80004005h
0x180003e89  jz      short loc_180003EE5
0x180003e8b  cmp     eax, 8007000Eh
0x180003e90  jz      short loc_180003EDC
0x180003e92  cmp     eax, 800703E4h
0x180003e97  jz      short loc_180003ECF
0x180003e99  cmp     eax, 800704C7h
0x180003e9e  jz      short loc_180003ECF
0x180003ea0  cmp     eax, 800B0004h
0x180003ea5  jz      short loc_180003ECF
0x180003ea7  cmp     eax, 800B010Bh
0x180003eac  jz      short loc_180003ECF
0x180003eae  test    eax, eax
0x180003eb0  jz      short loc_180003ED3
0x180003eb2  cmp     eax, edi
0x180003eb4  jz      short loc_180003EC6
0x180003eb6  cmp     eax, 0C0F81h
0x180003ebb  jnz     short loc_180003EE5
0x180003ebd  mov     dword ptr [r8], 1F60h
0x180003ec4  jmp     short loc_180003EEC
0x180003ec6  mov     dword ptr [r8], 1F63h
0x180003ecd  jmp     short loc_180003EEC
0x180003ecf  mov     [rcx+6Ch], r15d
0x180003ed3  mov     dword ptr [r8], 1F62h
0x180003eda  jmp     short loc_180003EEC
0x180003edc  mov     dword ptr [r8], 1F4Eh
0x180003ee3  jmp     short loc_180003EEC
0x180003ee5  mov     dword ptr [r8], 1F61h
0x180003eec  test    dword ptr [rcx+6Ch], 80000000h
0x180003ef3  jnz     short loc_180003F0C
0x180003ef5  cmp     [rcx+6Ch], edi
0x180003ef8  jz      short loc_180003F0C
0x180003efa  mov     r8d, edi; unsigned int
0x180003efd  lea     rdx, ?c_szPropEnableShortcutGleam@@3QBGB; "EnableShortcutGleam"
0x180003f04  mov     rcx, rbp; struct ISubscriptionItem *
0x180003f07  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x180003f0c  cmp     [rbx+0FCh], r15d
0x180003f13  jz      loc_180004120
0x180003f19  lea     rcx, [rsp+6A8h+pvarg]; pvarg
0x180003f1e  call    cs:__imp_VariantInit
0x180003f24  mov     r8d, edi; unsigned int
0x180003f27  lea     rdx, ?c_szPropEmailFlags@@3QBGB; "EmailFlags"
0x180003f2e  mov     rcx, rbp; struct ISubscriptionItem *
0x180003f31  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x180003f36  mov     rcx, [rbx+78h]; struct IXMLElement *
0x180003f3a  lea     r8, [rsp+6A8h+pvarg]; struct tagVARIANT *
0x180003f3f  call    ?GetXMLAttribute@@YAJPEAUIXMLElement@@PEBGPEAUtagVARIANT@@@Z; GetXMLAttribute(IXMLElement *,ushort const *,tagVARIANT *)
0x180003f44  test    eax, eax
0x180003f46  js      short loc_180003F67
0x180003f48  mov     r8, qword ptr [rsp+6A8h+pvarg+8]; unsigned __int16 *
0x180003f4d  lea     rdx, ?c_szPropURL@@3QBGB; "URL"
0x180003f54  mov     rcx, rbp; struct ISubscriptionItem *
0x180003f57  call    ?WriteOLESTR@@YAJPEAUISubscriptionItem@@PEBG1@Z; WriteOLESTR(ISubscriptionItem *,ushort const *,ushort const *)
0x180003f5c  lea     rcx, [rsp+6A8h+pvarg]; pvarg
0x180003f61  call    cs:__imp_VariantClear
0x180003f67  mov     rcx, [rbx+0A0h]; psz
0x180003f6e  test    rcx, rcx
0x180003f71  jz      short loc_180003FA0
0x180003f73  call    cs:__imp_SysAllocString
0x180003f79  mov     rdi, rax
0x180003f7c  test    rax, rax
0x180003f7f  jz      short loc_180003FA0
0x180003f81  mov     r8, [rbx+0A0h]; unsigned __int16 *
0x180003f88  lea     rdx, ?c_szPropEmailTitle@@3QBGB; "EmailTitle"
0x180003f8f  mov     rcx, rbp; struct ISubscriptionItem *
0x180003f92  call    ?WriteOLESTR@@YAJPEAUISubscriptionItem@@PEBG1@Z; WriteOLESTR(ISubscriptionItem *,ushort const *,ushort const *)
0x180003f97  mov     rcx, rdi; bstrString
0x180003f9a  call    cs:__imp_SysFreeString
0x180003fa0  mov     edx, [rbx+6Ch]; int
0x180003fa3  test    edx, edx
0x180003fa5  jns     short loc_180003FBC
0x180003fa7  cmp     [rbx+0D8h], r15
0x180003fae  jnz     short loc_180003FBC
0x180003fb0  call    ?GetErrorMessage@CCDLAgent@@QEAAPEAGJ@Z; CCDLAgent::GetErrorMessage(long)
0x180003fb5  mov     [rbx+0D8h], rax
0x180003fbc  mov     rcx, [rbx+0A8h]; psz
0x180003fc3  test    rcx, rcx
0x180003fc6  jz      loc_180004111
0x180003fcc  call    cs:__imp_SysAllocString
0x180003fd2  mov     rdi, rax
0x180003fd5  test    rax, rax
0x180003fd8  jz      loc_180004111
0x180003fde  mov     rcx, [rbx+0D8h]
0x180003fe5  test    rcx, rcx
0x180003fe8  jz      loc_1800040F1
0x180003fee  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003ff2  mov     rax, rsi
0x180003ff5  inc     rax
0x180003ff8  cmp     [rcx+rax*2], r15w
0x180003ffd  jnz     short loc_180003FF5
0x180003fff  lea     ecx, [rax-1]
0x180004002  test    ecx, ecx
0x180004004  jz      short loc_180004034
0x180004006  mov     r8, [rbx+0D8h]
0x18000400d  cmp     word ptr [r8+rcx*2], 2Eh ; '.'
0x180004013  ja      short loc_180004034
0x180004015  movzx   eax, word ptr [r8+rcx*2]
0x18000401a  mov     r9, 400000002400h
0x180004024  bt      r9, rax
0x180004028  jnb     short loc_180004034
0x18000402a  mov     [r8+rcx*2], r15w
0x18000402f  add     ecx, 0FFFFFFFFh
0x180004032  jnz     short loc_180004006
0x180004034  mov     rcx, cs:g_hinstMUI; hInstance
0x18000403b  lea     r8, [rsp+6A8h+Buffer]; lpBuffer
0x180004040  mov     r9d, 104h; cchBufferMax
0x180004046  mov     edx, 1F56h; uID
0x18000404b  call    cs:__imp_LoadStringW
0x180004051  test    eax, eax
0x180004053  jle     loc_1800040F1
0x180004059  mov     r9, [rbx+0D8h]
0x180004060  lea     r8, [rsp+6A8h+Buffer]; unsigned __int16 *
0x180004065  mov     edx, 208h; unsigned __int64
0x18000406a  lea     rcx, [rsp+6A8h+var_448]; unsigned __int16 *
0x180004072  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004077  lea     rcx, [rsp+6A8h+var_448]
0x18000407f  mov     rax, rsi
0x180004082  inc     rax
0x180004085  cmp     [rcx+rax*2], r15w
0x18000408a  jnz     short loc_180004082
0x18000408c  inc     rsi
0x18000408f  cmp     [rdi+rsi*2], r15w
0x180004094  jnz     short loc_18000408C
0x180004096  lea     r14, [rsi+4]
0x18000409a  xor     ecx, ecx; uFlags
0x18000409c  add     r14, rax
0x18000409f  mov     r14d, r14d
0x1800040a2  lea     rdx, [r14+r14]; uBytes
0x1800040a6  call    cs:__imp_LocalAlloc
0x1800040ac  mov     rsi, rax
0x1800040af  test    rax, rax
0x1800040b2  jz      short loc_1800040F1
0x1800040b4  lea     r9, [rsp+6A8h+var_448]
0x1800040bc  mov     [rsp+6A8h+var_688], rdi
0x1800040c1  lea     r8, aSWs; "%s%ws"
0x1800040c8  mov     edx, r14d; unsigned __int64
0x1800040cb  mov     rcx, rax; unsigned __int16 *
0x1800040ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800040d3  mov     rcx, rdi; bstrString
0x1800040d6  call    cs:__imp_SysFreeString
0x1800040dc  mov     rcx, rsi; psz
0x1800040df  call    cs:__imp_SysAllocString
0x1800040e5  mov     rcx, rsi; hMem
0x1800040e8  mov     rdi, rax
0x1800040eb  call    cs:__imp_LocalFree
0x1800040f1  mov     r8, rdi; unsigned __int16 *
0x1800040f4  lea     rdx, ?c_szPropEmailAbstract@@3QBGB; "EmailAbstract"
0x1800040fb  mov     rcx, rbp; struct ISubscriptionItem *
0x1800040fe  call    ?WriteOLESTR@@YAJPEAUISubscriptionItem@@PEBG1@Z; WriteOLESTR(ISubscriptionItem *,ushort const *,ushort const *)
0x180004103  test    rdi, rdi
0x180004106  jz      short loc_180004111
0x180004108  mov     rcx, rdi; bstrString
0x18000410b  call    cs:__imp_SysFreeString
0x180004111  xor     r8d, r8d; int
0x180004114  mov     [rbx+6Ch], r15d
0x180004118  mov     rcx, rbp; struct ISubscriptionItem *
0x18000411b  call    ?WriteSCODE@@YAJPEAUISubscriptionItem@@PEBGJ@Z; WriteSCODE(ISubscriptionItem *,ushort const *,long)
0x180004120  and     dword ptr [rbx+2Ch], 0FFFFFFFBh
0x180004124  xor     eax, eax
0x180004126  mov     rcx, [rsp+6A8h+var_38]
0x18000412e  xor     rcx, rsp; StackCookie
0x180004131  call    __security_check_cookie
0x180004136  mov     rbx, [rsp+6A8h+arg_18]
0x18000413e  add     rsp, 680h
0x180004145  pop     r15
0x180004147  pop     r14
0x180004149  pop     rdi
0x18000414a  pop     rsi
0x18000414b  pop     rbp
0x18000414c  retn
```
