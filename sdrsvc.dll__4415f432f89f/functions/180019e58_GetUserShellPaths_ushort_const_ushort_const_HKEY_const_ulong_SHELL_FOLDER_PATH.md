# GetUserShellPaths(ushort const *,ushort const *,HKEY__ * const,ulong *,SHELL_FOLDER_PATH * *)

- ea: `0x180019e58`
- end: `0x18001a185`
- name: `?GetUserShellPaths@@YAJPEBG0QEAUHKEY__@@PEAKPEAPEAUSHELL_FOLDER_PATH@@@Z`
- size: `813`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, HKEY, unsigned int *, struct SHELL_FOLDER_PATH **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800190bc`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180015f34`
- `0x180019e58`
- `0x18001a388`
- `0x18001b4c0`
- `0x18001f624`
- `0x18001fc5c`
- `0x18001fcc0`
- `0x180020488`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019f01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019f01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019f47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a12c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a14b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019f47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a12c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a14b`

## string_xrefs

- `0x180019e88`: `GetUserShellPaths`

## pseudocode

```c
__int64 __fastcall GetUserShellPaths(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        HKEY a3,
        unsigned int *a4,
        struct SHELL_FOLDER_PATH **a5)
{
  void *v7; // r12
  unsigned __int16 *v8; // rbx
  __int16 v9; // ax
  struct SHELL_FOLDER_PATH *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  const unsigned __int16 *v14; // r9
  const WCHAR *v15; // r13
  __int16 v16; // ax
  int StringFromRegistry; // eax
  int v18; // r8d
  const unsigned __int16 *v19; // r9
  int v20; // eax
  bool v21; // sf
  unsigned __int16 **v22; // rbx
  unsigned __int16 **v23; // rcx
  unsigned int v24; // ebx
  __int64 v25; // r14
  LPVOID *v26; // r15
  LPVOID *v27; // r14
  unsigned int v28; // ebx
  unsigned __int16 *v30; // [rsp+28h] [rbp-A1h]
  const unsigned __int16 *v31; // [rsp+30h] [rbp-99h]
  const unsigned __int16 *v32; // [rsp+38h] [rbp-91h]
  const unsigned __int16 *v33; // [rsp+40h] [rbp-89h]
  const unsigned __int16 *v34; // [rsp+48h] [rbp-81h]
  const unsigned __int16 *v35; // [rsp+50h] [rbp-79h]
  const unsigned __int16 *v36; // [rsp+58h] [rbp-71h]
  LPVOID pv; // [rsp+68h] [rbp-61h] BYREF
  __int64 v38; // [rsp+70h] [rbp-59h]
  unsigned __int16 *v39; // [rsp+78h] [rbp-51h] BYREF
  __int64 v40; // [rsp+80h] [rbp-49h]
  LPVOID v41[2]; // [rsp+88h] [rbp-41h] BYREF
  int v42; // [rsp+98h] [rbp-31h] BYREF
  __int16 v43; // [rsp+9Ch] [rbp-2Dh]
  __int16 v44; // [rsp+9Eh] [rbp-2Bh]
  int v45; // [rsp+128h] [rbp+5Fh]

  v45 = (int)a1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v42, "GetUserShellPaths", 175, 1);
  v7 = 0;
  v8 = (unsigned __int16 *)qword_180028260;
  v39 = (unsigned __int16 *)qword_180028260;
  v9 = 185;
  v40 = 0;
  v41[0] = qword_180028260;
  v41[1] = 0;
  if ( !a1 || (v43 = 185, v9 = 186, !a2) || (v43 = 186, v9 = 187, !a5) )
  {
    v42 = -2147024809;
    goto LABEL_38;
  }
  v42 = 0;
  v43 = 187;
  v10 = (struct SHELL_FOLDER_PATH *)CoTaskMemAlloc(0x140u);
  v9 = 191;
  if ( !v10 )
  {
    v42 = -2147024882;
LABEL_38:
    v44 = v9;
    goto LABEL_39;
  }
  v42 = 0;
  v11 = 0;
  v43 = 191;
  do
  {
    v12 = v11++;
    v12 *= 2;
    *((_QWORD *)v10 + v12) = 0;
    *((_QWORD *)v10 + v12 + 1) = 0;
  }
  while ( v11 != 20 );
  v13 = 0;
  while ( 1 )
  {
    CoTaskMemFree(v7);
    v7 = 0;
    v38 = (unsigned int)v13;
    pv = 0;
    if ( LODWORD(off_18002D3F0[5 * v13 + 4]) )
    {
      v15 = off_18002D3F0[5 * v13];
    }
    else
    {
      v42 = CBsString::Set((CBsString *)v41, (const struct _GUID *)&off_18002D3F0[5 * v13 + 2]);
      v16 = 209;
      if ( v42 < 0 )
        break;
      v15 = (const WCHAR *)v41[0];
      v43 = 209;
    }
    if ( a3 )
    {
      StringFromRegistry = ReadStringFromRegistry(a3, v15, (unsigned __int16 **)&pv, 0);
      if ( StringFromRegistry >= 0 )
      {
        v7 = pv;
        if ( (_DWORD)v40 )
        {
          LODWORD(v40) = 0;
          *v8 = 0;
        }
        v42 = CBsString::Append((CBsString *)&v39, (unsigned __int16 *)v7);
        v21 = v42 < 0;
        v16 = 228;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_SSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            v18,
            v45,
            (__int64)off_18002D3F0[5 * v13],
            StringFromRegistry);
        v20 = CBsString::SetPath(
                (CBsString *)&v39,
                a2,
                off_18002D3F0[5 * v13 + 1],
                v19,
                v30,
                v31,
                v32,
                v33,
                v34,
                v35,
                v36);
        v7 = pv;
        v21 = v20 < 0;
        v42 = v20;
        v16 = 224;
      }
    }
    else
    {
      v42 = CBsString::SetPath(
              (CBsString *)&v39,
              a2,
              off_18002D3F0[5 * v13 + 1],
              v14,
              v30,
              v31,
              v32,
              v33,
              v34,
              v35,
              v36);
      v21 = v42 < 0;
      v16 = 233;
    }
    if ( v21 )
      break;
    v22 = (unsigned __int16 **)((char *)v10 + 16 * v38);
    v43 = v16;
    v42 = SdSafeDuplicateStr(v22, v15);
    v16 = 236;
    if ( v42 < 0 )
      break;
    v23 = v22 + 1;
    v43 = 236;
    v8 = v39;
    v42 = SdSafeDuplicateStr(v23, v39);
    v16 = 237;
    if ( v42 < 0 )
      break;
    v13 = (unsigned int)(v13 + 1);
    v43 = 237;
    if ( (unsigned int)v13 >= 0x14 )
    {
      *a5 = v10;
      *a4 = 20;
      goto LABEL_39;
    }
  }
  v24 = 0;
  v44 = v16;
  do
  {
    v25 = 16LL * v24;
    v26 = (LPVOID *)((char *)v10 + v25);
    if ( (struct SHELL_FOLDER_PATH *)((char *)v10 + v25) && *v26 )
    {
      CoTaskMemFree(*v26);
      *v26 = 0;
    }
    v27 = (LPVOID *)((char *)v10 + v25 + 8);
    if ( v27 && *v27 )
    {
      CoTaskMemFree(*v27);
      *v27 = 0;
    }
    ++v24;
  }
  while ( v24 < 0x14 );
  CoTaskMemFree(v10);
LABEL_39:
  CoTaskMemFree(v7);
  v28 = v42;
  CBsString::_Release(v41);
  CBsString::_Release((LPVOID *)&v39);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v42);
  return v28;
}

```

## disassembly

```asm
0x180019e58  mov     rax, rsp
0x180019e5b  mov     [rax+20h], r9
0x180019e5f  mov     [rax+18h], r8
0x180019e63  mov     [rax+10h], rdx
0x180019e67  mov     [rax+8], rcx
0x180019e6b  push    rbp
0x180019e6c  push    rbx
0x180019e6d  push    rsi
0x180019e6e  push    rdi
0x180019e6f  push    r12
0x180019e71  push    r13
0x180019e73  push    r14
0x180019e75  push    r15
0x180019e77  lea     rbp, [rax-57h]
0x180019e7b  sub     rsp, 0D8h
0x180019e82  mov     rdi, rdx
0x180019e85  mov     rsi, rcx
0x180019e88  lea     rdx, aGetusershellpa; "GetUserShellPaths"
0x180019e8f  mov     r9d, 1; unsigned __int16
0x180019e95  lea     rcx, [rbp+4Fh+var_80]; this
0x180019e99  mov     r8d, 0AFh; unsigned __int16
0x180019e9f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180019ea4  xor     r12d, r12d
0x180019ea7  lea     rbx, qword_180028260
0x180019eae  mov     [rbp+4Fh+var_A0], rbx
0x180019eb2  mov     eax, 0B9h
0x180019eb7  mov     [rbp+4Fh+var_98], r12
0x180019ebb  mov     [rbp+4Fh+var_90], rbx
0x180019ebf  mov     [rbp+4Fh+var_88], r12
0x180019ec3  test    rsi, rsi
0x180019ec6  jz      loc_18001A13D
0x180019ecc  mov     [rbp+4Fh+var_7C], ax
0x180019ed0  mov     eax, 0BAh
0x180019ed5  test    rdi, rdi
0x180019ed8  jz      loc_18001A13D
0x180019ede  mov     r14, [rbp+4Fh+arg_20]
0x180019ee2  mov     [rbp+4Fh+var_7C], ax
0x180019ee6  mov     eax, 0BBh
0x180019eeb  test    r14, r14
0x180019eee  jz      loc_18001A13D
0x180019ef4  mov     ecx, 140h; cb
0x180019ef9  mov     [rbp+4Fh+var_80], r12d
0x180019efd  mov     [rbp+4Fh+var_7C], ax
0x180019f01  call    cs:__imp_CoTaskMemAlloc
0x180019f07  mov     rdi, rax
0x180019f0a  test    rax, rax
0x180019f0d  mov     eax, 0BFh
0x180019f12  jz      loc_18001A134
0x180019f18  mov     [rbp+4Fh+var_80], r12d
0x180019f1c  xor     ecx, ecx
0x180019f1e  mov     [rbp+4Fh+var_7C], ax
0x180019f22  mov     rax, rcx
0x180019f25  inc     rcx
0x180019f28  add     rax, rax
0x180019f2b  mov     [rdi+rax*8], r12
0x180019f2f  mov     [rdi+rax*8+8], r12
0x180019f34  cmp     rcx, 14h
0x180019f38  jnz     short loc_180019F22
0x180019f3a  xor     r15d, r15d
0x180019f3d  mov     rcx, r12; pv
0x180019f40  lea     r13, off_18002D3F0; "Local AppData"
0x180019f47  call    cs:__imp_CoTaskMemFree
0x180019f4d  xor     r12d, r12d
0x180019f50  mov     eax, r15d
0x180019f53  lea     rsi, [r15+r15*4]
0x180019f57  mov     [rbp+4Fh+var_A8], rax
0x180019f5b  mov     [rbp+4Fh+pv], r12
0x180019f5f  cmp     [r13+rsi*8+20h], r12d
0x180019f64  jz      short loc_180019F6D
0x180019f66  mov     r13, [r13+rsi*8+0]
0x180019f6b  jmp     short loc_180019F99
0x180019f6d  lea     rdx, ds:10h[rsi*8]
0x180019f75  add     rdx, r13; struct _GUID *
0x180019f78  lea     rcx, [rbp+4Fh+var_90]; this
0x180019f7c  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x180019f81  mov     [rbp+4Fh+var_80], eax
0x180019f84  test    eax, eax
0x180019f86  mov     eax, 0D1h
0x180019f8b  js      loc_18001A0D6
0x180019f91  mov     r13, [rbp+4Fh+var_90]
0x180019f95  mov     [rbp+4Fh+var_7C], ax
0x180019f99  mov     rax, [rbp+4Fh+hKey]
0x180019f9d  test    rax, rax
0x180019fa0  jz      loc_18001A04B
0x180019fa6  xor     r9d, r9d; int
0x180019fa9  lea     r8, [rbp+4Fh+pv]; unsigned __int16 **
0x180019fad  mov     rdx, r13; lpValueName
0x180019fb0  mov     rcx, rax; hKey
0x180019fb3  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180019fb8  test    eax, eax
0x180019fba  jns     short loc_18001A01D
0x180019fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fc3  lea     rdx, WPP_GLOBAL_Control
0x180019fca  lea     rbx, off_18002D3F0; "Local AppData"
0x180019fd1  cmp     rcx, rdx
0x180019fd4  jz      short loc_180019FFB
0x180019fd6  test    byte ptr [rcx+1Ch], 40h
0x180019fda  jz      short loc_180019FFB
0x180019fdc  mov     r9, [rbp+4Fh+arg_0]
0x180019fe0  mov     edx, 0Ah
0x180019fe5  mov     rcx, [rcx+10h]
0x180019fe9  mov     [rsp+28h], eax; unsigned __int16 *
0x180019fed  mov     rax, [rbx+rsi*8]
0x180019ff1  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180019ff6  call    WPP_SF_SSd
0x180019ffb  mov     r8, [rbx+rsi*8+8]; unsigned __int16 *
0x18001a000  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001a004  mov     rdx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x18001a008  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001a00d  mov     r12, [rbp+4Fh+pv]
0x18001a011  test    eax, eax
0x18001a013  mov     [rbp+4Fh+var_80], eax
0x18001a016  mov     eax, 0E0h
0x18001a01b  jmp     short loc_18001A06E
0x18001a01d  cmp     dword ptr [rbp+4Fh+var_98], 0
0x18001a021  mov     r12, [rbp+4Fh+pv]
0x18001a025  jz      short loc_18001A033
0x18001a027  xor     eax, eax
0x18001a029  mov     dword ptr [rbp+4Fh+var_98], 0
0x18001a030  mov     [rbx], ax
0x18001a033  mov     rdx, r12; unsigned __int16 *
0x18001a036  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001a03a  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18001a03f  mov     [rbp+4Fh+var_80], eax
0x18001a042  test    eax, eax
0x18001a044  mov     eax, 0E4h
0x18001a049  jmp     short loc_18001A06E
0x18001a04b  mov     rdx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x18001a04f  lea     rbx, off_18002D3F0; "Local AppData"
0x18001a056  mov     r8, [rbx+rsi*8+8]; unsigned __int16 *
0x18001a05b  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001a05f  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001a064  mov     [rbp+4Fh+var_80], eax
0x18001a067  test    eax, eax
0x18001a069  mov     eax, 0E9h
0x18001a06e  js      short loc_18001A0D6
0x18001a070  mov     rbx, [rbp+4Fh+var_A8]
0x18001a074  mov     rdx, r13; unsigned __int16 *
0x18001a077  shl     rbx, 4
0x18001a07b  add     rbx, rdi
0x18001a07e  mov     [rbp+4Fh+var_7C], ax
0x18001a082  mov     rcx, rbx; unsigned __int16 **
0x18001a085  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x18001a08a  mov     [rbp+4Fh+var_80], eax
0x18001a08d  test    eax, eax
0x18001a08f  mov     eax, 0ECh
0x18001a094  js      short loc_18001A0D6
0x18001a096  lea     rcx, [rbx+8]; unsigned __int16 **
0x18001a09a  mov     [rbp+4Fh+var_7C], ax
0x18001a09e  mov     rbx, [rbp+4Fh+var_A0]
0x18001a0a2  mov     rdx, rbx; unsigned __int16 *
0x18001a0a5  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x18001a0aa  mov     [rbp+4Fh+var_80], eax
0x18001a0ad  test    eax, eax
0x18001a0af  mov     eax, 0EDh
0x18001a0b4  js      short loc_18001A0D6
0x18001a0b6  inc     r15d
0x18001a0b9  mov     [rbp+4Fh+var_7C], ax
0x18001a0bd  cmp     r15d, 14h
0x18001a0c1  jb      loc_180019F3D
0x18001a0c7  mov     rax, [rbp+4Fh+arg_18]
0x18001a0cb  mov     [r14], rdi
0x18001a0ce  mov     dword ptr [rax], 14h
0x18001a0d4  jmp     short loc_18001A148
0x18001a0d6  xor     ebx, ebx
0x18001a0d8  mov     [rbp+4Fh+var_7A], ax
0x18001a0dc  mov     rsi, rdi
0x18001a0df  mov     r14d, ebx
0x18001a0e2  shl     r14, 4
0x18001a0e6  lea     r15, [r14+rdi]
0x18001a0ea  test    r15, r15
0x18001a0ed  jz      short loc_18001A104
0x18001a0ef  mov     rcx, [r15]; pv
0x18001a0f2  test    rcx, rcx
0x18001a0f5  jz      short loc_18001A104
0x18001a0f7  call    cs:__imp_CoTaskMemFree
0x18001a0fd  mov     qword ptr [r15], 0
0x18001a104  add     r14, 8
0x18001a108  add     r14, rsi
0x18001a10b  jz      short loc_18001A122
0x18001a10d  mov     rcx, [r14]; pv
0x18001a110  test    rcx, rcx
0x18001a113  jz      short loc_18001A122
0x18001a115  call    cs:__imp_CoTaskMemFree
0x18001a11b  mov     qword ptr [r14], 0
0x18001a122  inc     ebx
0x18001a124  cmp     ebx, 14h
0x18001a127  jb      short loc_18001A0DF
0x18001a129  mov     rcx, rdi; pv
0x18001a12c  call    cs:__imp_CoTaskMemFree
0x18001a132  jmp     short loc_18001A148
0x18001a134  mov     [rbp+4Fh+var_80], 8007000Eh
0x18001a13b  jmp     short loc_18001A144
0x18001a13d  mov     [rbp+4Fh+var_80], 80070057h
0x18001a144  mov     [rbp+4Fh+var_7A], ax
0x18001a148  mov     rcx, r12; pv
0x18001a14b  call    cs:__imp_CoTaskMemFree
0x18001a151  mov     ebx, [rbp+4Fh+var_80]
0x18001a154  lea     rcx, [rbp+4Fh+var_90]; this
0x18001a158  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001a15d  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001a161  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001a166  lea     rcx, [rbp+4Fh+var_80]; this
0x18001a16a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001a16f  mov     eax, ebx
0x18001a171  add     rsp, 0D8h
0x18001a178  pop     r15
0x18001a17a  pop     r14
0x18001a17c  pop     r13
0x18001a17e  pop     r12
0x18001a180  pop     rdi
0x18001a181  pop     rsi
0x18001a182  pop     rbx
0x18001a183  pop     rbp
0x18001a184  retn
```
