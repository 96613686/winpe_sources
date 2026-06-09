# EnumSearchRoots(CAutoDSA<SEARCH_ROOT> *)

- ea: `0x180021f84`
- end: `0x180022198`
- name: `?EnumSearchRoots@@YAJPEAV?$CAutoDSA@USEARCH_ROOT@@@@@Z`
- size: `532`
- prototype: `__int64 __fastcall(HDSA *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180022840`
- `0x180022aa0`

## callees

- `0x180002a30`
- `0x180003290`
- `0x180003840`
- `0x1800218fc`
- `0x180021f84`
- `0x18002ffdc`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021ff2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021ff2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022181`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022181`

## pseudocode

```c
__int64 __fastcall EnumSearchRoots(HDSA *a1)
{
  unsigned int v2; // r8d
  HRESULT v3; // ebx
  __int64 v4; // rcx
  BOOL v5; // eax
  __int64 v7; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  __int128 v10; // [rsp+48h] [rbp-18h] BYREF
  __int64 v11; // [rsp+88h] [rbp+28h] BYREF
  __int64 v12; // [rsp+90h] [rbp+30h] BYREF
  __int64 v13; // [rsp+98h] [rbp+38h] BYREF

  if ( (unsigned int)CDSA_Base<SEARCH_ROOT>::Create(a1, 4) )
  {
    hKey = 0;
    v3 = RegOpenKeyOpt(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search\\PHSearchConnectors", v2, &hKey);
    if ( v3 >= 0 )
    {
      ppv = 0;
      v3 = CoCreateInstance(&CLSID_CSearchManager, 0, 0x15u, &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69, &ppv);
      if ( v3 >= 0 )
      {
        v7 = 0;
        v3 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 *))(*(_QWORD *)ppv + 80LL))(
               ppv,
               L"SystemIndex",
               &v7);
        if ( v3 >= 0 )
        {
          v13 = 0;
          v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 224LL))(v7, &v13);
          if ( v3 >= 0 )
          {
            v11 = 0;
            v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 48LL))(v13, &v11);
            if ( v3 >= 0 )
            {
              v4 = v11;
              if ( v11 )
              {
                v12 = 0;
                while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v4 + 24LL))(
                           v4,
                           1,
                           &v12) )
                {
                  v10 = 0;
                  v3 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 48LL))(v12, (char *)&v10 + 8);
                  if ( v3 >= 0 )
                  {
                    LODWORD(v10) = GetTemplateVersion(hKey, *((PCWSTR *)&v10 + 1));
                    v3 = CAutoDSA<SEARCH_ROOT>::AppendAndClearItem(a1, &v10);
                    CoTaskMemFree(*((LPVOID *)&v10 + 1));
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
                  if ( v3 < 0 )
                    goto LABEL_18;
                  v4 = v11;
                }
                if ( *a1 )
                  v5 = DSA_Sort(*a1, SEARCH_ROOT::DSACompare, 0);
                else
                  v5 = 0;
                v3 = !v5 ? 0x80004005 : 0;
LABEL_18:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
              }
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180021f84  push    rbp
0x180021f86  push    rbx
0x180021f87  push    rdi
0x180021f88  mov     rbp, rsp
0x180021f8b  sub     rsp, 60h
0x180021f8f  mov     edx, 4
0x180021f94  mov     rdi, rcx
0x180021f97  call    ?Create@?$CDSA_Base@USEARCH_ROOT@@@@QEAAHH@Z; CDSA_Base<SEARCH_ROOT>::Create(int)
0x180021f9c  test    eax, eax
0x180021f9e  jz      loc_180022189
0x180021fa4  lea     r9, [rbp+hKey]; HKEY *
0x180021fa8  mov     [rbp+hKey], 0
0x180021fb0  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows Search\\PH"...
0x180021fb7  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180021fbe  call    ?RegOpenKeyOpt@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; RegOpenKeyOpt(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180021fc3  mov     ebx, eax
0x180021fc5  test    eax, eax
0x180021fc7  js      loc_18002218E
0x180021fcd  xor     edx, edx; pUnkOuter
0x180021fcf  mov     [rbp+var_28], 0
0x180021fd7  lea     rax, [rbp+var_28]
0x180021fdb  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x180021fe2  mov     [rsp+60h+ppv], rax; ppv
0x180021fe7  lea     rcx, CLSID_CSearchManager; rclsid
0x180021fee  lea     r8d, [rdx+15h]; dwClsContext
0x180021ff2  call    cs:__imp_CoCreateInstance
0x180021ff8  mov     ebx, eax
0x180021ffa  test    eax, eax
0x180021ffc  js      loc_180022178
0x180022002  mov     rcx, [rbp+var_28]
0x180022006  lea     r8, [rbp+var_30]
0x18002200a  mov     [rbp+var_30], 0
0x180022012  lea     rdx, aSystemindex; "SystemIndex"
0x180022019  mov     rax, [rcx]
0x18002201c  mov     rax, [rax+50h]
0x180022020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022025  mov     ebx, eax
0x180022027  test    eax, eax
0x180022029  js      loc_180022168
0x18002202f  mov     rcx, [rbp+var_30]
0x180022033  lea     rdx, [rbp+arg_18]
0x180022037  mov     [rbp+arg_18], 0
0x18002203f  mov     rax, [rcx]
0x180022042  mov     rax, [rax+0E0h]
0x180022049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002204e  mov     ebx, eax
0x180022050  test    eax, eax
0x180022052  js      loc_180022158
0x180022058  mov     rcx, [rbp+arg_18]
0x18002205c  lea     rdx, [rbp+arg_8]
0x180022060  mov     [rbp+arg_8], 0
0x180022068  mov     rax, [rcx]
0x18002206b  mov     rax, [rax+30h]
0x18002206f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022074  mov     ebx, eax
0x180022076  test    eax, eax
0x180022078  js      loc_180022148
0x18002207e  mov     rcx, [rbp+arg_8]
0x180022082  test    rcx, rcx
0x180022085  jz      loc_180022148
0x18002208b  mov     [rbp+arg_10], 0
0x180022093  mov     rax, [rcx]
0x180022096  lea     r8, [rbp+arg_10]
0x18002209a  xor     r9d, r9d
0x18002209d  mov     rax, [rax+18h]
0x1800220a1  lea     edx, [r9+1]
0x1800220a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220aa  test    eax, eax
0x1800220ac  jnz     short loc_180022111
0x1800220ae  mov     rcx, [rbp+arg_10]
0x1800220b2  lea     rdx, [rbp+pv]
0x1800220b6  xorps   xmm0, xmm0
0x1800220b9  movups  xmmword ptr [rbp-18h], xmm0
0x1800220bd  mov     rax, [rcx]
0x1800220c0  mov     rax, [rax+30h]
0x1800220c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220c9  mov     ebx, eax
0x1800220cb  test    eax, eax
0x1800220cd  js      short loc_1800220F7
0x1800220cf  mov     rdx, [rbp+pv]; pszIn
0x1800220d3  mov     rcx, [rbp+hKey]; hkey
0x1800220d7  call    ?GetTemplateVersion@@YAKPEAUHKEY__@@PEBG@Z; GetTemplateVersion(HKEY__ *,ushort const *)
0x1800220dc  lea     rdx, [rbp+var_18]
0x1800220e0  mov     [rbp+var_18], eax
0x1800220e3  mov     rcx, rdi
0x1800220e6  call    ?AppendAndClearItem@?$CAutoDSA@USEARCH_ROOT@@@@QEAAJPEAUSEARCH_ROOT@@@Z; CAutoDSA<SEARCH_ROOT>::AppendAndClearItem(SEARCH_ROOT *)
0x1800220eb  mov     rcx, [rbp+pv]; pv
0x1800220ef  mov     ebx, eax
0x1800220f1  call    cs:__imp_CoTaskMemFree
0x1800220f7  mov     rcx, [rbp+arg_10]
0x1800220fb  mov     rax, [rcx]
0x1800220fe  mov     rax, [rax+10h]
0x180022102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022107  test    ebx, ebx
0x180022109  js      short loc_180022138
0x18002210b  mov     rcx, [rbp+arg_8]
0x18002210f  jmp     short loc_180022093
0x180022111  mov     rcx, [rdi]; pdsa
0x180022114  test    rcx, rcx
0x180022117  jz      short loc_18002212A
0x180022119  xor     r8d, r8d; lParam
0x18002211c  lea     rdx, ?DSACompare@SEARCH_ROOT@@SAHPEBU1@0_J@Z; pfnCompare
0x180022123  call    DSA_Sort
0x180022128  jmp     short loc_18002212C
0x18002212a  xor     eax, eax
0x18002212c  neg     eax
0x18002212e  sbb     ebx, ebx
0x180022130  not     ebx
0x180022132  and     ebx, 80004005h
0x180022138  mov     rcx, [rbp+arg_8]
0x18002213c  mov     rax, [rcx]
0x18002213f  mov     rax, [rax+10h]
0x180022143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022148  mov     rcx, [rbp+arg_18]
0x18002214c  mov     rax, [rcx]
0x18002214f  mov     rax, [rax+10h]
0x180022153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022158  mov     rcx, [rbp+var_30]
0x18002215c  mov     rax, [rcx]
0x18002215f  mov     rax, [rax+10h]
0x180022163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022168  mov     rcx, [rbp+var_28]
0x18002216c  mov     rax, [rcx]
0x18002216f  mov     rax, [rax+10h]
0x180022173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022178  mov     rcx, [rbp+hKey]; hKey
0x18002217c  test    rcx, rcx
0x18002217f  jz      short loc_18002218E
0x180022181  call    cs:__imp_RegCloseKey
0x180022187  jmp     short loc_18002218E
0x180022189  mov     ebx, 8007000Eh
0x18002218e  mov     eax, ebx
0x180022190  add     rsp, 60h
0x180022194  pop     rdi
0x180022195  pop     rbx
0x180022196  pop     rbp
0x180022197  retn
```
