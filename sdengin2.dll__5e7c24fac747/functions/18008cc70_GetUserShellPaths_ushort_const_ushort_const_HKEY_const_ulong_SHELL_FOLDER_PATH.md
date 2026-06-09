# GetUserShellPaths(ushort const *,ushort const *,HKEY__ * const,ulong *,SHELL_FOLDER_PATH * *)

- ea: `0x18008cc70`
- end: `0x18008cf8d`
- name: `?GetUserShellPaths@@YAJPEBG0QEAUHKEY__@@PEAKPEAPEAUSHELL_FOLDER_PATH@@@Z`
- size: `797`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, HKEY, unsigned int *, struct SHELL_FOLDER_PATH **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18008bef4`

## callees

- `0x180009a98`
- `0x18006fe84`
- `0x18006ff8c`
- `0x1800709ec`
- `0x1800885bc`
- `0x18008cc70`
- `0x18008d0d4`
- `0x18009a0bc`
- `0x18009a24c`
- `0x18009a378`
- `0x18009ae34`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008cd65`
- `ole32!CoTaskMemFree` at `0x18008cf25`
- `ole32!CoTaskMemFree` at `0x18008cf53`
- `ole32!CoTaskMemFree` at `0x18008cd65`
- `ole32!CoTaskMemFree` at `0x18008cf25`
- `ole32!CoTaskMemFree` at `0x18008cf53`
- `ole32!CoTaskMemAlloc` at `0x18008cd1c`
- `ole32!CoTaskMemAlloc` at `0x18008cd1c`

## string_xrefs

- `0x18008cca0`: `GetUserShellPaths`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v31, "GetUserShellPaths", 175, 1);
  v29[0] = (unsigned __int16 *)qword_1800E8530;
  v7 = 0;
  v30[0] = qword_1800E8530;
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
    if ( LODWORD(off_1800FC940[5 * i + 4]) )
    {
      v13 = off_1800FC940[5 * i];
    }
    else
    {
      v31 = CBsString::Set((CBsString *)v30, (const struct _GUID *)&qword_1800FC950[5 * i]);
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
            (__int64)off_1800FC940[5 * i],
            StringFromRegistry);
        v17 = CBsString::SetPath((CBsString *)v29, a2, off_1800FC940[5 * i + 1], 0, 0, 0, v23, v24, v25, v26, v27);
        v7 = pv;
        v18 = v17 < 0;
        v31 = v17;
        v14 = 224;
      }
    }
    else
    {
      v31 = CBsString::SetPath((CBsString *)v29, a2, off_1800FC940[5 * i + 1], 0, 0, 0, v23, v24, v25, v26, v27);
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
0x18008cc70  mov     rax, rsp
0x18008cc73  mov     [rax+20h], r9
0x18008cc77  mov     [rax+18h], r8
0x18008cc7b  mov     [rax+10h], rdx
0x18008cc7f  mov     [rax+8], rcx
0x18008cc83  push    rbp
0x18008cc84  push    rbx
0x18008cc85  push    rsi
0x18008cc86  push    rdi
0x18008cc87  push    r12
0x18008cc89  push    r13
0x18008cc8b  push    r14
0x18008cc8d  push    r15
0x18008cc8f  lea     rbp, [rax-57h]
0x18008cc93  sub     rsp, 0C8h
0x18008cc9a  mov     rbx, rdx
0x18008cc9d  mov     rdi, rcx
0x18008cca0  lea     rdx, aGetusershellpa; "GetUserShellPaths"
0x18008cca7  mov     r9d, 1; unsigned __int16
0x18008ccad  lea     rcx, [rbp+4Fh+var_78]; this
0x18008ccb1  mov     r8d, 0AFh; unsigned __int16
0x18008ccb7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008ccbc  xor     r13d, r13d
0x18008ccbf  lea     rax, qword_1800E8530
0x18008ccc6  mov     [rbp+4Fh+var_98], rax
0x18008ccca  mov     r15d, r13d
0x18008cccd  mov     [rbp+4Fh+var_88], rax
0x18008ccd1  mov     eax, 0B9h
0x18008ccd6  mov     [rbp+4Fh+var_90], r13
0x18008ccda  mov     [rbp+4Fh+var_80], r13
0x18008ccde  test    rdi, rdi
0x18008cce1  jz      loc_18008CF45
0x18008cce7  mov     [rbp+4Fh+var_74], ax
0x18008cceb  mov     eax, 0BAh
0x18008ccf0  test    rbx, rbx
0x18008ccf3  jz      loc_18008CF45
0x18008ccf9  mov     r14, [rbp+4Fh+arg_20]
0x18008ccfd  mov     [rbp+4Fh+var_74], ax
0x18008cd01  mov     eax, 0BBh
0x18008cd06  test    r14, r14
0x18008cd09  jz      loc_18008CF45
0x18008cd0f  mov     ecx, 140h; cb
0x18008cd14  mov     [rbp+4Fh+var_78], r13d
0x18008cd18  mov     [rbp+4Fh+var_74], ax
0x18008cd1c  call    cs:__imp_CoTaskMemAlloc
0x18008cd22  mov     rdi, rax
0x18008cd25  test    rax, rax
0x18008cd28  mov     eax, 0BFh
0x18008cd2d  jz      loc_18008CF3C
0x18008cd33  mov     [rbp+4Fh+var_78], r13d
0x18008cd37  mov     ecx, r13d
0x18008cd3a  mov     [rbp+4Fh+var_74], ax
0x18008cd3e  mov     rax, rcx
0x18008cd41  inc     rcx
0x18008cd44  add     rax, rax
0x18008cd47  mov     [rdi+rax*8], r13
0x18008cd4b  mov     [rdi+rax*8+8], r13
0x18008cd50  cmp     rcx, 14h
0x18008cd54  jnz     short loc_18008CD3E
0x18008cd56  mov     esi, r13d
0x18008cd59  cmp     esi, 14h
0x18008cd5c  jnb     loc_18008CF2D
0x18008cd62  mov     rcx, r15; pv
0x18008cd65  call    cs:__imp_CoTaskMemFree
0x18008cd6b  mov     r12d, esi
0x18008cd6e  lea     rcx, off_1800FC940; "Local AppData"
0x18008cd75  mov     r15, r13
0x18008cd78  mov     [rbp+4Fh+pv], r13
0x18008cd7c  lea     rbx, [r12+r12*4]
0x18008cd80  cmp     [rcx+rbx*8+20h], r13d
0x18008cd85  jz      short loc_18008CD8D
0x18008cd87  mov     r13, [rcx+rbx*8]
0x18008cd8b  jmp     short loc_18008CDBD
0x18008cd8d  lea     rdx, [rcx+10h]
0x18008cd91  lea     rdx, [rdx+rbx*8]; struct _GUID *
0x18008cd95  lea     rcx, [rbp+4Fh+var_88]; this
0x18008cd99  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x18008cd9e  mov     [rbp+4Fh+var_78], eax
0x18008cda1  test    eax, eax
0x18008cda3  mov     eax, 0D1h
0x18008cda8  js      loc_18008CEF6
0x18008cdae  mov     r13, [rbp+4Fh+var_88]
0x18008cdb2  lea     rcx, off_1800FC940; "Local AppData"
0x18008cdb9  mov     [rbp+4Fh+var_74], ax
0x18008cdbd  mov     rax, [rbp+4Fh+hKey]
0x18008cdc1  test    rax, rax
0x18008cdc4  jz      loc_18008CE72
0x18008cdca  xor     r9d, r9d; int
0x18008cdcd  lea     r8, [rbp+4Fh+pv]; unsigned __int16 **
0x18008cdd1  mov     rdx, r13; lpValueName
0x18008cdd4  mov     rcx, rax; hKey
0x18008cdd7  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18008cddc  test    eax, eax
0x18008cdde  jns     short loc_18008CE56
0x18008cde0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cde7  lea     rdx, WPP_GLOBAL_Control
0x18008cdee  lea     r15, off_1800FC940; "Local AppData"
0x18008cdf5  cmp     rcx, rdx
0x18008cdf8  jz      short loc_18008CE1F
0x18008cdfa  test    byte ptr [rcx+1Ch], 40h
0x18008cdfe  jz      short loc_18008CE1F
0x18008ce00  mov     r9, [rbp+4Fh+arg_0]
0x18008ce04  mov     edx, 0Ah
0x18008ce09  mov     rcx, [rcx+10h]
0x18008ce0d  mov     [rsp+28h], eax
0x18008ce11  mov     rax, [r15+rbx*8]
0x18008ce15  mov     [rsp+100h+var_E0], rax
0x18008ce1a  call    WPP_SF_SSd
0x18008ce1f  mov     r8, [r15+rbx*8+8]; unsigned __int16 *
0x18008ce24  lea     rcx, [rbp+4Fh+var_98]; this
0x18008ce28  mov     rdx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x18008ce2c  xor     r9d, r9d; unsigned __int16 *
0x18008ce2f  mov     qword ptr [rsp+28h], 0; unsigned __int16 *
0x18008ce38  mov     [rsp+100h+var_E0], 0; unsigned __int16 *
0x18008ce41  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18008ce46  mov     r15, [rbp+4Fh+pv]
0x18008ce4a  test    eax, eax
0x18008ce4c  mov     [rbp+4Fh+var_78], eax
0x18008ce4f  mov     eax, 0E0h
0x18008ce54  jmp     short loc_18008CEA3
0x18008ce56  mov     r15, [rbp+4Fh+pv]
0x18008ce5a  lea     rcx, [rbp+4Fh+var_98]; this
0x18008ce5e  mov     rdx, r15; unsigned __int16 *
0x18008ce61  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18008ce66  mov     [rbp+4Fh+var_78], eax
0x18008ce69  test    eax, eax
0x18008ce6b  mov     eax, 0E4h
0x18008ce70  jmp     short loc_18008CEA3
0x18008ce72  mov     r8, [rcx+rbx*8+8]; unsigned __int16 *
0x18008ce77  xor     r9d, r9d; unsigned __int16 *
0x18008ce7a  mov     rdx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x18008ce7e  lea     rcx, [rbp+4Fh+var_98]; this
0x18008ce82  mov     qword ptr [rsp+28h], 0; unsigned __int16 *
0x18008ce8b  mov     [rsp+100h+var_E0], 0; unsigned __int16 *
0x18008ce94  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18008ce99  mov     [rbp+4Fh+var_78], eax
0x18008ce9c  test    eax, eax
0x18008ce9e  mov     eax, 0E9h
0x18008cea3  js      short loc_18008CEF2
0x18008cea5  add     r12, r12
0x18008cea8  mov     [rbp+4Fh+var_74], ax
0x18008ceac  mov     rdx, r13; unsigned __int16 *
0x18008ceaf  lea     rbx, [rdi+r12*8]
0x18008ceb3  mov     rcx, rbx; unsigned __int16 **
0x18008ceb6  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x18008cebb  xor     r13d, r13d
0x18008cebe  mov     [rbp+4Fh+var_78], eax
0x18008cec1  test    eax, eax
0x18008cec3  mov     eax, 0ECh
0x18008cec8  js      short loc_18008CEF6
0x18008ceca  mov     rdx, [rbp+4Fh+var_98]; unsigned __int16 *
0x18008cece  lea     rcx, [rbx+8]; unsigned __int16 **
0x18008ced2  mov     [rbp+4Fh+var_74], ax
0x18008ced6  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x18008cedb  mov     [rbp+4Fh+var_78], eax
0x18008cede  test    eax, eax
0x18008cee0  mov     eax, 0EDh
0x18008cee5  js      short loc_18008CEF6
0x18008cee7  mov     [rbp+4Fh+var_74], ax
0x18008ceeb  inc     esi
0x18008ceed  jmp     loc_18008CD59
0x18008cef2  xor     esi, esi
0x18008cef4  jmp     short loc_18008CEF9
0x18008cef6  mov     esi, r13d
0x18008cef9  mov     r14, rdi
0x18008cefc  mov     [rbp+4Fh+var_72], ax
0x18008cf00  mov     ebx, esi
0x18008cf02  shl     rbx, 4
0x18008cf06  lea     rcx, [rbx+rdi]; unsigned __int16 **
0x18008cf0a  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x18008cf0f  lea     rcx, [r14+8]
0x18008cf13  add     rcx, rbx; unsigned __int16 **
0x18008cf16  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x18008cf1b  inc     esi
0x18008cf1d  cmp     esi, 14h
0x18008cf20  jb      short loc_18008CF00
0x18008cf22  mov     rcx, rdi; pv
0x18008cf25  call    cs:__imp_CoTaskMemFree
0x18008cf2b  jmp     short loc_18008CF50
0x18008cf2d  mov     rax, [rbp+4Fh+arg_18]
0x18008cf31  mov     [r14], rdi
0x18008cf34  mov     dword ptr [rax], 14h
0x18008cf3a  jmp     short loc_18008CF50
0x18008cf3c  mov     [rbp+4Fh+var_78], 8007000Eh
0x18008cf43  jmp     short loc_18008CF4C
0x18008cf45  mov     [rbp+4Fh+var_78], 80070057h
0x18008cf4c  mov     [rbp+4Fh+var_72], ax
0x18008cf50  mov     rcx, r15; pv
0x18008cf53  call    cs:__imp_CoTaskMemFree
0x18008cf59  mov     ebx, [rbp+4Fh+var_78]
0x18008cf5c  lea     rcx, [rbp+4Fh+var_88]; this
0x18008cf60  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18008cf65  lea     rcx, [rbp+4Fh+var_98]; this
0x18008cf69  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18008cf6e  lea     rcx, [rbp+4Fh+var_78]; this
0x18008cf72  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008cf77  mov     eax, ebx
0x18008cf79  add     rsp, 0C8h
0x18008cf80  pop     r15
0x18008cf82  pop     r14
0x18008cf84  pop     r13
0x18008cf86  pop     r12
0x18008cf88  pop     rdi
0x18008cf89  pop     rsi
0x18008cf8a  pop     rbx
0x18008cf8b  pop     rbp
0x18008cf8c  retn
```
