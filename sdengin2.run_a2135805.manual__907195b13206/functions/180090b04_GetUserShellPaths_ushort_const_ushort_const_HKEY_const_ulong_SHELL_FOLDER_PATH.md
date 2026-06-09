# GetUserShellPaths(ushort const *,ushort const *,HKEY__ * const,ulong *,SHELL_FOLDER_PATH * *)

- ea: `0x180090b04`
- end: `0x180090e3a`
- name: `?GetUserShellPaths@@YAJPEBG0QEAUHKEY__@@PEAKPEAPEAUSHELL_FOLDER_PATH@@@Z`
- size: `822`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, HKEY, unsigned int *, struct SHELL_FOLDER_PATH **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18008fce0`

## callees

- `0x180009d0c`
- `0x180072e08`
- `0x180072f14`
- `0x1800739f8`
- `0x18008c040`
- `0x180090b04`
- `0x180090f90`
- `0x18009e750`
- `0x18009e904`
- `0x18009ea34`
- `0x18009f560`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180090bff`
- `ole32!CoTaskMemFree` at `0x180090dc5`
- `ole32!CoTaskMemFree` at `0x180090df9`
- `ole32!CoTaskMemFree` at `0x180090bff`
- `ole32!CoTaskMemFree` at `0x180090dc5`
- `ole32!CoTaskMemFree` at `0x180090df9`
- `ole32!CoTaskMemAlloc` at `0x180090bb0`
- `ole32!CoTaskMemAlloc` at `0x180090bb0`

## string_xrefs

- `0x180090b34`: `GetUserShellPaths`

## pseudocode

```c
__int64 __fastcall GetUserShellPaths(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        HKEY a3,
        unsigned int *a4,
        struct SHELL_FOLDER_PATH **a5)
{
  void *v7; // r15
  __int16 v8; // ax
  struct SHELL_FOLDER_PATH *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned int i; // esi
  const WCHAR *v13; // r13
  __int16 v14; // ax
  int StringFromRegistry; // eax
  int v16; // r8d
  int v17; // eax
  bool v18; // sf
  unsigned int v19; // esi
  __int64 v20; // rbx
  unsigned int v21; // ebx
  const unsigned __int16 *v23; // [rsp+38h] [rbp-81h]
  const unsigned __int16 *v24; // [rsp+40h] [rbp-79h]
  const unsigned __int16 *v25; // [rsp+48h] [rbp-71h]
  const unsigned __int16 *v26; // [rsp+50h] [rbp-69h]
  const unsigned __int16 *v27; // [rsp+58h] [rbp-61h]
  LPVOID pv; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v29[2]; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v30[2]; // [rsp+80h] [rbp-39h] BYREF
  int v31; // [rsp+90h] [rbp-29h] BYREF
  __int16 v32; // [rsp+94h] [rbp-25h]
  __int16 v33; // [rsp+96h] [rbp-23h]
  int v34; // [rsp+118h] [rbp+5Fh]

  v34 = (int)a1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v31, "GetUserShellPaths", 0xAFu, 1u);
  v29[0] = (unsigned __int16 *)qword_1800EE510;
  v7 = 0;
  v30[0] = qword_1800EE510;
  v8 = 185;
  v29[1] = 0;
  v30[1] = 0;
  if ( !a1 || (v32 = 185, v8 = 186, !a2) || (v32 = 186, v8 = 187, !a5) )
  {
    v31 = -2147024809;
    goto LABEL_33;
  }
  v31 = 0;
  v32 = 187;
  v9 = (struct SHELL_FOLDER_PATH *)CoTaskMemAlloc(0x140u);
  v8 = 191;
  if ( !v9 )
  {
    v31 = -2147024882;
LABEL_33:
    v33 = v8;
    goto LABEL_34;
  }
  v31 = 0;
  v10 = 0;
  v32 = 191;
  do
  {
    v11 = v10++;
    v11 *= 2;
    *((_QWORD *)v9 + v11) = 0;
    *((_QWORD *)v9 + v11 + 1) = 0;
  }
  while ( v10 != 20 );
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x14 )
    {
      *a5 = v9;
      *a4 = 20;
      goto LABEL_34;
    }
    CoTaskMemFree(v7);
    v7 = 0;
    pv = 0;
    if ( LODWORD(off_180102A40[5 * i + 4]) )
    {
      v13 = off_180102A40[5 * i];
    }
    else
    {
      v31 = CBsString::Set((CBsString *)v30, (const struct _GUID *)&qword_180102A50[5 * i]);
      v14 = 209;
      if ( v31 < 0 )
        break;
      v13 = (const WCHAR *)v30[0];
      v32 = 209;
    }
    if ( a3 )
    {
      StringFromRegistry = ReadStringFromRegistry(a3, v13, (unsigned __int16 **)&pv, 0);
      if ( StringFromRegistry >= 0 )
      {
        v7 = pv;
        v31 = CBsString::Set((CBsString *)v29, (const unsigned __int16 *)pv);
        v18 = v31 < 0;
        v14 = 228;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_SSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            v16,
            v34,
            (__int64)off_180102A40[5 * i],
            StringFromRegistry);
        v17 = CBsString::SetPath((CBsString *)v29, a2, off_180102A40[5 * i + 1], 0, 0, 0, v23, v24, v25, v26, v27);
        v7 = pv;
        v18 = v17 < 0;
        v31 = v17;
        v14 = 224;
      }
    }
    else
    {
      v31 = CBsString::SetPath((CBsString *)v29, a2, off_180102A40[5 * i + 1], 0, 0, 0, v23, v24, v25, v26, v27);
      v18 = v31 < 0;
      v14 = 233;
    }
    if ( v18 )
    {
      v19 = 0;
      goto LABEL_27;
    }
    v32 = v14;
    v31 = SdSafeDuplicateStr((unsigned __int16 **)v9 + 2 * i, v13);
    v14 = 236;
    if ( v31 < 0 )
      break;
    v32 = 236;
    v31 = SdSafeDuplicateStr((unsigned __int16 **)v9 + 2 * i + 1, v29[0]);
    v14 = 237;
    if ( v31 < 0 )
      break;
    v32 = 237;
  }
  v19 = 0;
LABEL_27:
  v33 = v14;
  do
  {
    v20 = 16LL * v19;
    SdFreeString((unsigned __int16 **)((char *)v9 + v20));
    SdFreeString((unsigned __int16 **)((char *)v9 + v20 + 8));
    ++v19;
  }
  while ( v19 < 0x14 );
  CoTaskMemFree(v9);
LABEL_34:
  CoTaskMemFree(v7);
  v21 = v31;
  CBsString::_Release((CBsString *)v30);
  CBsString::_Release((CBsString *)v29);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v31);
  return v21;
}

```

## disassembly

```asm
0x180090b04  mov     rax, rsp
0x180090b07  mov     [rax+20h], r9
0x180090b0b  mov     [rax+18h], r8
0x180090b0f  mov     [rax+10h], rdx
0x180090b13  mov     [rax+8], rcx
0x180090b17  push    rbp
0x180090b18  push    rbx
0x180090b19  push    rsi
0x180090b1a  push    rdi
0x180090b1b  push    r12
0x180090b1d  push    r13
0x180090b1f  push    r14
0x180090b21  push    r15
0x180090b23  lea     rbp, [rax-57h]
0x180090b27  sub     rsp, 0C8h
0x180090b2e  mov     rbx, rdx
0x180090b31  mov     rdi, rcx
0x180090b34  lea     rdx, aGetusershellpa; "GetUserShellPaths"
0x180090b3b  mov     r9d, 1; unsigned __int16
0x180090b41  lea     rcx, [rbp+4Fh+var_78]; this
0x180090b45  mov     r8d, 0AFh; unsigned __int16
0x180090b4b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180090b50  xor     r13d, r13d
0x180090b53  lea     rax, qword_1800EE510
0x180090b5a  mov     [rbp+4Fh+var_98], rax
0x180090b5e  mov     r15d, r13d
0x180090b61  mov     [rbp+4Fh+var_88], rax
0x180090b65  mov     eax, 0B9h
0x180090b6a  mov     [rbp+4Fh+var_90], r13
0x180090b6e  mov     [rbp+4Fh+var_80], r13
0x180090b72  test    rdi, rdi
0x180090b75  jz      loc_180090DEB
0x180090b7b  mov     [rbp+4Fh+var_74], ax
0x180090b7f  mov     eax, 0BAh
0x180090b84  test    rbx, rbx
0x180090b87  jz      loc_180090DEB
0x180090b8d  mov     r14, [rbp+4Fh+arg_20]
0x180090b91  mov     [rbp+4Fh+var_74], ax
0x180090b95  mov     eax, 0BBh
0x180090b9a  test    r14, r14
0x180090b9d  jz      loc_180090DEB
0x180090ba3  mov     ecx, 140h; cb
0x180090ba8  mov     [rbp+4Fh+var_78], r13d
0x180090bac  mov     [rbp+4Fh+var_74], ax
0x180090bb0  call    cs:__imp_CoTaskMemAlloc
0x180090bb7  nop     dword ptr [rax+rax+00h]
0x180090bbc  mov     rdi, rax
0x180090bbf  test    rax, rax
0x180090bc2  mov     eax, 0BFh
0x180090bc7  jz      loc_180090DE2
0x180090bcd  mov     [rbp+4Fh+var_78], r13d
0x180090bd1  mov     ecx, r13d
0x180090bd4  mov     [rbp+4Fh+var_74], ax
0x180090bd8  mov     rax, rcx
0x180090bdb  inc     rcx
0x180090bde  add     rax, rax
0x180090be1  mov     [rdi+rax*8], r13
0x180090be5  mov     [rdi+rax*8+8], r13
0x180090bea  cmp     rcx, 14h
0x180090bee  jnz     short loc_180090BD8
0x180090bf0  mov     esi, r13d
0x180090bf3  cmp     esi, 14h
0x180090bf6  jnb     loc_180090DD3
0x180090bfc  mov     rcx, r15; pv
0x180090bff  call    cs:__imp_CoTaskMemFree
0x180090c06  nop     dword ptr [rax+rax+00h]
0x180090c0b  mov     r12d, esi
0x180090c0e  lea     rcx, off_180102A40; "Local AppData"
0x180090c15  mov     r15, r13
0x180090c18  mov     [rbp+4Fh+pv], r13
0x180090c1c  lea     rbx, [r12+r12*4]
0x180090c20  cmp     [rcx+rbx*8+20h], r13d
0x180090c25  jz      short loc_180090C2D
0x180090c27  mov     r13, [rcx+rbx*8]
0x180090c2b  jmp     short loc_180090C5D
0x180090c2d  lea     rdx, [rcx+10h]
0x180090c31  lea     rdx, [rdx+rbx*8]; struct _GUID *
0x180090c35  lea     rcx, [rbp+4Fh+var_88]; this
0x180090c39  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x180090c3e  mov     [rbp+4Fh+var_78], eax
0x180090c41  test    eax, eax
0x180090c43  mov     eax, 0D1h
0x180090c48  js      loc_180090D96
0x180090c4e  mov     r13, [rbp+4Fh+var_88]
0x180090c52  lea     rcx, off_180102A40; "Local AppData"
0x180090c59  mov     [rbp+4Fh+var_74], ax
0x180090c5d  mov     rax, [rbp+4Fh+hKey]
0x180090c61  test    rax, rax
0x180090c64  jz      loc_180090D12
0x180090c6a  xor     r9d, r9d; int
0x180090c6d  lea     r8, [rbp+4Fh+pv]; unsigned __int16 **
0x180090c71  mov     rdx, r13; lpValueName
0x180090c74  mov     rcx, rax; hKey
0x180090c77  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180090c7c  test    eax, eax
0x180090c7e  jns     short loc_180090CF6
0x180090c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180090c87  lea     rdx, WPP_GLOBAL_Control
0x180090c8e  lea     r15, off_180102A40; "Local AppData"
0x180090c95  cmp     rcx, rdx
0x180090c98  jz      short loc_180090CBF
0x180090c9a  test    byte ptr [rcx+1Ch], 40h
0x180090c9e  jz      short loc_180090CBF
0x180090ca0  mov     r9, [rbp+4Fh+arg_0]
0x180090ca4  mov     edx, 0Ah
0x180090ca9  mov     rcx, [rcx+10h]
0x180090cad  mov     [rsp+28h], eax
0x180090cb1  mov     rax, [r15+rbx*8]
0x180090cb5  mov     [rsp+100h+var_E0], rax
0x180090cba  call    WPP_SF_SSd
0x180090cbf  mov     r8, [r15+rbx*8+8]; unsigned __int16 *
0x180090cc4  lea     rcx, [rbp+4Fh+var_98]; this
0x180090cc8  mov     rdx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x180090ccc  xor     r9d, r9d; unsigned __int16 *
0x180090ccf  mov     qword ptr [rsp+28h], 0; unsigned __int16 *
0x180090cd8  mov     [rsp+100h+var_E0], 0; unsigned __int16 *
0x180090ce1  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180090ce6  mov     r15, [rbp+4Fh+pv]
0x180090cea  test    eax, eax
0x180090cec  mov     [rbp+4Fh+var_78], eax
0x180090cef  mov     eax, 0E0h
0x180090cf4  jmp     short loc_180090D43
0x180090cf6  mov     r15, [rbp+4Fh+pv]
0x180090cfa  lea     rcx, [rbp+4Fh+var_98]; this
0x180090cfe  mov     rdx, r15; unsigned __int16 *
0x180090d01  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180090d06  mov     [rbp+4Fh+var_78], eax
0x180090d09  test    eax, eax
0x180090d0b  mov     eax, 0E4h
0x180090d10  jmp     short loc_180090D43
0x180090d12  mov     r8, [rcx+rbx*8+8]; unsigned __int16 *
0x180090d17  xor     r9d, r9d; unsigned __int16 *
0x180090d1a  mov     rdx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x180090d1e  lea     rcx, [rbp+4Fh+var_98]; this
0x180090d22  mov     qword ptr [rsp+28h], 0; unsigned __int16 *
0x180090d2b  mov     [rsp+100h+var_E0], 0; unsigned __int16 *
0x180090d34  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180090d39  mov     [rbp+4Fh+var_78], eax
0x180090d3c  test    eax, eax
0x180090d3e  mov     eax, 0E9h
0x180090d43  js      short loc_180090D92
0x180090d45  add     r12, r12
0x180090d48  mov     [rbp+4Fh+var_74], ax
0x180090d4c  mov     rdx, r13; unsigned __int16 *
0x180090d4f  lea     rbx, [rdi+r12*8]
0x180090d53  mov     rcx, rbx; unsigned __int16 **
0x180090d56  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x180090d5b  xor     r13d, r13d
0x180090d5e  mov     [rbp+4Fh+var_78], eax
0x180090d61  test    eax, eax
0x180090d63  mov     eax, 0ECh
0x180090d68  js      short loc_180090D96
0x180090d6a  mov     rdx, [rbp+4Fh+var_98]; unsigned __int16 *
0x180090d6e  lea     rcx, [rbx+8]; unsigned __int16 **
0x180090d72  mov     [rbp+4Fh+var_74], ax
0x180090d76  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x180090d7b  mov     [rbp+4Fh+var_78], eax
0x180090d7e  test    eax, eax
0x180090d80  mov     eax, 0EDh
0x180090d85  js      short loc_180090D96
0x180090d87  mov     [rbp+4Fh+var_74], ax
0x180090d8b  inc     esi
0x180090d8d  jmp     loc_180090BF3
0x180090d92  xor     esi, esi
0x180090d94  jmp     short loc_180090D99
0x180090d96  mov     esi, r13d
0x180090d99  mov     r14, rdi
0x180090d9c  mov     [rbp+4Fh+var_72], ax
0x180090da0  mov     ebx, esi
0x180090da2  shl     rbx, 4
0x180090da6  lea     rcx, [rbx+rdi]; unsigned __int16 **
0x180090daa  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x180090daf  lea     rcx, [r14+8]
0x180090db3  add     rcx, rbx; unsigned __int16 **
0x180090db6  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x180090dbb  inc     esi
0x180090dbd  cmp     esi, 14h
0x180090dc0  jb      short loc_180090DA0
0x180090dc2  mov     rcx, rdi; pv
0x180090dc5  call    cs:__imp_CoTaskMemFree
0x180090dcc  nop     dword ptr [rax+rax+00h]
0x180090dd1  jmp     short loc_180090DF6
0x180090dd3  mov     rax, [rbp+4Fh+arg_18]
0x180090dd7  mov     [r14], rdi
0x180090dda  mov     dword ptr [rax], 14h
0x180090de0  jmp     short loc_180090DF6
0x180090de2  mov     [rbp+4Fh+var_78], 8007000Eh
0x180090de9  jmp     short loc_180090DF2
0x180090deb  mov     [rbp+4Fh+var_78], 80070057h
0x180090df2  mov     [rbp+4Fh+var_72], ax
0x180090df6  mov     rcx, r15; pv
0x180090df9  call    cs:__imp_CoTaskMemFree
0x180090e00  nop     dword ptr [rax+rax+00h]
0x180090e05  mov     ebx, [rbp+4Fh+var_78]
0x180090e08  lea     rcx, [rbp+4Fh+var_88]; this
0x180090e0c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180090e11  lea     rcx, [rbp+4Fh+var_98]; this
0x180090e15  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180090e1a  lea     rcx, [rbp+4Fh+var_78]; this
0x180090e1e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180090e23  mov     eax, ebx
0x180090e25  add     rsp, 0C8h
0x180090e2c  pop     r15
0x180090e2e  pop     r14
0x180090e30  pop     r13
0x180090e32  pop     r12
0x180090e34  pop     rdi
0x180090e35  pop     rsi
0x180090e36  pop     rbx
0x180090e37  pop     rbp
0x180090e38  retn
```
