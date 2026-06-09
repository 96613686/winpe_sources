# _CreateReadOnlyPropStoreForSid(void *,IPropertyStore * *)

- ea: `0x18000ed10`
- end: `0x18000ef4f`
- name: `?_CreateReadOnlyPropStoreForSid@@YAJPEAXPEAPEAUIPropertyStore@@@Z`
- size: `575`
- prototype: `__int64 __fastcall(void *, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006ba0`

## callees

- `0x18000b410`
- `0x18000b598`
- `0x18000b828`
- `0x18000c240`
- `0x18000e8b4`
- `0x18000ed10`
- `0x1800100e4`
- `0x180010ce4`
- `0x180011ca4`
- `0x1800168f8`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eeef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eeef`
- `PROPSYS!InitPropVariantFromBuffer` at `0x18000eeae`
- `PROPSYS!InitPropVariantFromBuffer` at `0x18000eeae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef1d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000eee4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000eee4`

## pseudocode

```c
__int64 __fastcall _CreateReadOnlyPropStoreForSid(void *a1, struct IPropertyStore **a2)
{
  int v3; // ebx
  int v4; // eax
  void *v5; // rdi
  WCHAR *v6; // xmm1_8
  __int64 i; // rbx
  _WORD *v8; // r9
  int v9; // eax
  bool v10; // al
  struct IPropertyStore *v11; // rcx
  UINT cb; // [rsp+30h] [rbp-D0h] BYREF
  struct IPropertyStore *v14; // [rsp+38h] [rbp-C8h] BYREF
  void *pv; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sids; // [rsp+48h] [rbp-B8h] BYREF
  struct _SID_INFO ppropvar; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v18[520]; // [rsp+70h] [rbp-90h] BYREF

  Sids = a1;
  *a2 = 0;
  v3 = -2147024809;
  if ( a1 )
  {
    pv = 0;
    v4 = LookupSids(1u, &Sids, &pv);
    v5 = pv;
    if ( pv )
    {
      if ( v4 < 0 )
      {
        return (unsigned int)v4;
      }
      else
      {
        v14 = 0;
        v6 = (WCHAR *)*((_QWORD *)pv + 2);
        *(_OWORD *)&ppropvar.pSid = *(_OWORD *)pv;
        ppropvar.pwzClass = v6;
        v3 = CreateReadOnlyPropertyStore(Sids, &ppropvar, &v14);
        if ( v3 >= 0 )
        {
          cb = 0;
          if ( (int)CSGetAccountRights(Sids, &cb) >= 0 )
          {
            for ( i = 0; i != 10; ++i )
              IPropertyStore_SetBool(
                v14,
                (char *)&xmmword_18001F490 + 36 * i,
                cb & *((_DWORD *)&xmmword_18001F490 + 9 * i + 7));
          }
          v8 = (_WORD *)*((_QWORD *)v5 + 1);
          if ( v8 && *v8 )
            v9 = StringCchPrintfW(v18, 0x201u, L"%s\\%s");
          else
            v9 = StringCchCopyW(v18, 0x201u, *((const unsigned __int16 **)v5 + 2));
          v3 = v9;
          if ( v9 >= 0 )
          {
            v10 = DontEnumerateForLogon(v14);
            IPropertyStore_SetBool(v14, &PKEY_SAM_DontEnumerateForLogon, v10);
            pv = 0;
            cb = 0;
            if ( (int)SHGetPictureFromDataFileForUser(v18, (unsigned __int8 **)&pv, &cb) >= 0 )
            {
              memset(&ppropvar, 0, 24);
              if ( InitPropVariantFromBuffer(pv, cb, &ppropvar.pSid) >= 0 )
              {
                LOWORD(ppropvar.pSid) = 65;
                ((void (__fastcall *)(struct IPropertyStore *, __int128 *, struct _SID_INFO *))v14->lpVtbl->SetValue)(
                  v14,
                  &PKEY_SAM_UserPicture,
                  &ppropvar);
                PropVariantClear(&ppropvar.pSid);
              }
              LocalFree(pv);
            }
            v11 = v14;
            *a2 = v14;
            ((void (__fastcall *)(struct IPropertyStore *))v11->lpVtbl->AddRef)(v11);
          }
          ((void (__fastcall *)(struct IPropertyStore *))v14->lpVtbl->Release)(v14);
        }
        CoTaskMemFree(v5);
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ed10  mov     [rsp-8+arg_10], rbx
0x18000ed15  push    rbp
0x18000ed16  push    rsi
0x18000ed17  push    rdi
0x18000ed18  push    r14
0x18000ed1a  push    r15
0x18000ed1c  lea     rbp, [rsp-390h]
0x18000ed24  sub     rsp, 490h
0x18000ed2b  mov     rax, cs:__security_cookie
0x18000ed32  xor     rax, rsp
0x18000ed35  mov     [rbp+3B0h+var_30], rax
0x18000ed3c  xor     r14d, r14d
0x18000ed3f  mov     [rsp+4B0h+Sids], rcx
0x18000ed44  mov     [rdx], r14
0x18000ed47  mov     rsi, rdx
0x18000ed4a  mov     ebx, 80070057h
0x18000ed4f  test    rcx, rcx
0x18000ed52  jz      loc_18000EF27
0x18000ed58  lea     r8, [rsp+4B0h+pv]; struct _SID_INFO **
0x18000ed5d  mov     [rsp+4B0h+pv], r14
0x18000ed62  lea     rdx, [rsp+4B0h+Sids]; Sids
0x18000ed67  lea     ecx, [r14+1]; Count
0x18000ed6b  call    ?LookupSids@@YAJKPEAPEAXPEAPEAU_SID_INFO@@@Z; LookupSids(ulong,void * *,_SID_INFO * *)
0x18000ed70  mov     rdi, [rsp+4B0h+pv]
0x18000ed75  test    rdi, rdi
0x18000ed78  jz      loc_18000EF27
0x18000ed7e  test    eax, eax
0x18000ed80  js      loc_18000EF25
0x18000ed86  mov     rcx, [rsp+4B0h+Sids]; pSid
0x18000ed8b  lea     r8, [rsp+4B0h+var_478]; struct IPropertyStore **
0x18000ed90  mov     [rsp+4B0h+var_478], r14
0x18000ed95  lea     rdx, [rsp+4B0h+ppropvar]; struct _SID_INFO
0x18000ed9a  movups  xmm0, xmmword ptr [rdi]
0x18000ed9d  movsd   xmm1, qword ptr [rdi+10h]
0x18000eda2  movaps  xmmword ptr [rsp+4B0h+ppropvar], xmm0
0x18000eda7  movsd   [rsp+4B0h+var_450], xmm1
0x18000edad  call    ?CreateReadOnlyPropertyStore@@YAJPEAXU_SID_INFO@@PEAPEAUIPropertyStore@@@Z; CreateReadOnlyPropertyStore(void *,_SID_INFO,IPropertyStore * *)
0x18000edb2  mov     ebx, eax
0x18000edb4  test    eax, eax
0x18000edb6  js      loc_18000EF1A
0x18000edbc  mov     rcx, [rsp+4B0h+Sids]; AccountSid
0x18000edc1  lea     rdx, [rsp+4B0h+cb]
0x18000edc6  mov     [rsp+4B0h+cb], r14d
0x18000edcb  call    CSGetAccountRights
0x18000edd0  test    eax, eax
0x18000edd2  js      short loc_18000EE03
0x18000edd4  mov     ebx, r14d
0x18000edd7  lea     r15, xmmword_18001F490
0x18000edde  mov     rcx, [rsp+4B0h+var_478]
0x18000ede3  lea     rax, [rbx+rbx*8]
0x18000ede7  mov     r8d, [r15+rax*4+1Ch]
0x18000edec  lea     rdx, [r15+rax*4]
0x18000edf0  and     r8d, [rsp+4B0h+cb]
0x18000edf5  call    IPropertyStore_SetBool
0x18000edfa  inc     rbx
0x18000edfd  cmp     rbx, 0Ah
0x18000ee01  jnz     short loc_18000EDDE
0x18000ee03  mov     r9, [rdi+8]
0x18000ee07  test    r9, r9
0x18000ee0a  jz      short loc_18000EE33
0x18000ee0c  cmp     [r9], r14w
0x18000ee10  jz      short loc_18000EE33
0x18000ee12  mov     rax, [rdi+10h]
0x18000ee16  lea     r8, aSS; "%s\\%s"
0x18000ee1d  mov     edx, 201h; unsigned __int64
0x18000ee22  mov     [rsp+4B0h+var_490], rax
0x18000ee27  lea     rcx, [rsp+4B0h+var_440]; unsigned __int16 *
0x18000ee2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ee31  jmp     short loc_18000EE46
0x18000ee33  mov     r8, [rdi+10h]; unsigned __int16 *
0x18000ee37  lea     rcx, [rsp+4B0h+var_440]; unsigned __int16 *
0x18000ee3c  mov     edx, 201h; unsigned __int64
0x18000ee41  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ee46  mov     ebx, eax
0x18000ee48  test    eax, eax
0x18000ee4a  js      loc_18000EF09
0x18000ee50  mov     rcx, [rsp+4B0h+var_478]; struct IPropertyStore *
0x18000ee55  call    ?DontEnumerateForLogon@@YA_NPEAUIPropertyStore@@@Z; DontEnumerateForLogon(IPropertyStore *)
0x18000ee5a  mov     rcx, [rsp+4B0h+var_478]
0x18000ee5f  lea     rdx, PKEY_SAM_DontEnumerateForLogon
0x18000ee66  movzx   r8d, al
0x18000ee6a  call    IPropertyStore_SetBool
0x18000ee6f  lea     r8, [rsp+4B0h+cb]; unsigned int *
0x18000ee74  mov     [rsp+4B0h+pv], r14
0x18000ee79  lea     rdx, [rsp+4B0h+pv]; unsigned __int8 **
0x18000ee7e  mov     [rsp+4B0h+cb], r14d
0x18000ee83  lea     rcx, [rsp+4B0h+var_440]; unsigned __int16 *
0x18000ee88  call    ?SHGetPictureFromDataFileForUser@@YAJPEBGPEAPEAEPEAK@Z; SHGetPictureFromDataFileForUser(ushort const *,uchar * *,ulong *)
0x18000ee8d  test    eax, eax
0x18000ee8f  js      short loc_18000EEF5
0x18000ee91  mov     edx, [rsp+4B0h+cb]; cb
0x18000ee95  lea     r8, [rsp+4B0h+ppropvar]; ppropvar
0x18000ee9a  mov     rcx, [rsp+4B0h+pv]; pv
0x18000ee9f  xorps   xmm0, xmm0
0x18000eea2  xor     eax, eax
0x18000eea4  movups  xmmword ptr [rsp+4B0h+ppropvar], xmm0
0x18000eea9  mov     [rsp+4B0h+var_450], rax
0x18000eeae  call    cs:__imp_InitPropVariantFromBuffer
0x18000eeb4  test    eax, eax
0x18000eeb6  js      short loc_18000EEEA
0x18000eeb8  mov     rcx, [rsp+4B0h+var_478]
0x18000eebd  lea     r8, [rsp+4B0h+ppropvar]
0x18000eec2  mov     eax, 41h ; 'A'
0x18000eec7  lea     rdx, PKEY_SAM_UserPicture
0x18000eece  mov     word ptr [rsp+4B0h+ppropvar], ax
0x18000eed3  mov     rax, [rcx]
0x18000eed6  mov     rax, [rax+30h]
0x18000eeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eedf  lea     rcx, [rsp+4B0h+ppropvar]; pvar
0x18000eee4  call    cs:__imp_PropVariantClear
0x18000eeea  mov     rcx, [rsp+4B0h+pv]; hMem
0x18000eeef  call    cs:__imp_LocalFree
0x18000eef5  mov     rcx, [rsp+4B0h+var_478]
0x18000eefa  mov     [rsi], rcx
0x18000eefd  mov     rax, [rcx]
0x18000ef00  mov     rax, [rax+8]
0x18000ef04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef09  mov     rcx, [rsp+4B0h+var_478]
0x18000ef0e  mov     rax, [rcx]
0x18000ef11  mov     rax, [rax+10h]
0x18000ef15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef1a  mov     rcx, rdi; pv
0x18000ef1d  call    cs:__imp_CoTaskMemFree
0x18000ef23  jmp     short loc_18000EF27
0x18000ef25  mov     ebx, eax
0x18000ef27  mov     eax, ebx
0x18000ef29  mov     rcx, [rbp+3B0h+var_30]
0x18000ef30  xor     rcx, rsp; StackCookie
0x18000ef33  call    __security_check_cookie
0x18000ef38  mov     rbx, [rsp+4B0h+arg_10]
0x18000ef40  add     rsp, 490h
0x18000ef47  pop     r15
0x18000ef49  pop     r14
0x18000ef4b  pop     rdi
0x18000ef4c  pop     rsi
0x18000ef4d  pop     rbp
0x18000ef4e  retn
```
