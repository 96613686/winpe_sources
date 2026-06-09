# _WinStationGetAllSessions(void *,ulong *,_EXECENV_ENUMINFOW * *,ulong *)

- ea: `0x180001d80`
- end: `0x18000200b`
- name: `?_WinStationGetAllSessions@@YAJPEAXPEAKPEAPEAU_EXECENV_ENUMINFOW@@1@Z`
- size: `651`
- prototype: `__int64 __fastcall(void *, unsigned int *, struct _EXECENV_ENUMINFOW **, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180002600`
- `0x18002c160`

## callees

- `0x180001d80`
- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000d870`
- `0x180025f38`
- `0x180032be6`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001eb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001eb8`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032db9`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032db9`

## string_xrefs

- `0x180001dd8`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall _WinStationGetAllSessions(
        void *a1,
        unsigned int *a2,
        struct _EXECENV_ENUMINFOW **a3,
        unsigned int *a4)
{
  unsigned int v7; // esi
  unsigned int v8; // r14d
  int AllSessions; // ebx
  void *v10; // rax
  void *v11; // rax
  SIZE_T v12; // rdi
  struct _EXECENV_ENUMINFOW *v13; // r13
  unsigned __int64 v14; // r14
  unsigned __int16 *v15; // rdi
  __int64 v16; // r11
  __int64 v17; // r11
  __int64 v18; // r11
  __int64 v19; // r11
  __int64 v21; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int16 v22[36]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v23; // [rsp+88h] [rbp+10h] BYREF
  struct _EXECENV_ENUMINFOW **v24; // [rsp+90h] [rbp+18h]
  unsigned int *v25; // [rsp+98h] [rbp+20h]

  v25 = a4;
  v24 = a3;
  v7 = 0;
  v23 = 0;
  v21 = 0;
  v8 = *a2;
  *a3 = 0;
  *a4 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v22, a1, 0);
  if ( CSmartPublicBinding::operator void *(v22) )
  {
    v10 = CSmartPublicBinding::operator void *(v22);
    AllSessions = RpcGetAllSessions(v10, a2, &v21, &v23);
    if ( AllSessions == -2147024809 && *a2 < v8 )
    {
      v11 = CSmartPublicBinding::operator void *(v22);
      AllSessions = RpcGetAllSessions(v11, a2, &v21, &v23);
    }
    if ( AllSessions >= 0 )
    {
      v12 = 344 * v23;
      v13 = (struct _EXECENV_ENUMINFOW *)LocalAlloc(0, v12);
      if ( v13 )
      {
        v14 = v12 / 0x158;
        if ( v23 )
        {
          do
          {
            if ( v7 >= (unsigned int)v14 )
              break;
            v15 = (unsigned __int16 *)((char *)v13 + 344 * v7);
            memset_0(v15, 0, 0x158u);
            *(_DWORD *)v15 = *(_DWORD *)(348LL * v7 + v21 + 4);
            *((_DWORD *)v15 + 19) = *(_DWORD *)(348LL * v7 + v21 + 80);
            *((_DWORD *)v15 + 1) = *(_DWORD *)(348LL * v7 + v21 + 8);
            StringCchCopyW(v15 + 4, 0x20u, (const unsigned __int16 *)(348LL * v7 + v21 + 12));
            StringCchCopyW(v15 + 40, 0x21u, (const unsigned __int16 *)(v16 + v21 + 84));
            StringCchCopyW(v15 + 73, 0x21u, (const unsigned __int16 *)(v17 + v21 + 150));
            StringCchCopyW(v15 + 106, 0x21u, (const unsigned __int16 *)(v18 + v21 + 216));
            AllSessions = StringCchCopyW(v15 + 139, 0x21u, (const unsigned __int16 *)(v19 + v21 + 282));
            ++v7;
          }
          while ( v7 < v23 );
        }
        *a3 = v13;
        *a4 = v14;
      }
      else
      {
        AllSessions = -2147024882;
      }
    }
    else
    {
      _DbgPrintMessage(8, "RpcGetAllSessions failed: 0x%x in %s", AllSessions, "_WinStationGetAllSessions");
    }
  }
  else
  {
    AllSessions = -2147467263;
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v22);
  return (unsigned int)AllSessions;
}

```

## disassembly

```asm
0x180001d80  mov     rax, rsp
0x180001d83  mov     [rax+20h], r9
0x180001d87  mov     [rax+18h], r8
0x180001d8b  push    rbx
0x180001d8c  push    rsi
0x180001d8d  push    rdi
0x180001d8e  push    r12
0x180001d90  push    r13
0x180001d92  push    r14
0x180001d94  push    r15
0x180001d96  sub     rsp, 40h
0x180001d9a  mov     r15, r9
0x180001d9d  mov     r12, r8
0x180001da0  mov     rdi, rdx
0x180001da3  xor     esi, esi
0x180001da5  mov     [rax+10h], esi
0x180001da8  mov     [rax-50h], rsi
0x180001dac  mov     r14d, [rdx]
0x180001daf  mov     [r8], rsi
0x180001db2  mov     [r9], esi
0x180001db5  xor     r8d, r8d; int
0x180001db8  mov     rdx, rcx; void *
0x180001dbb  lea     rcx, [rax-48h]; this
0x180001dbf  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180001dc4  lea     rcx, [rsp+78h+var_48]; unsigned __int16 *
0x180001dc9  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180001dce  test    rax, rax
0x180001dd1  jnz     short loc_180001DEC
0x180001dd3  mov     ebx, 80004001h
0x180001dd8  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180001ddf  lea     ecx, [rsi+8]; int
0x180001de2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001de7  jmp     loc_180001FEE
0x180001dec  lea     rcx, [rsp+78h+var_48]; unsigned __int16 *
0x180001df1  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180001df6  mov     rcx, rax
0x180001df9  lea     r9, [rsp+78h+arg_8]
0x180001e01  lea     r8, [rsp+78h+var_50]
0x180001e06  mov     rdx, rdi
0x180001e09  call    RpcGetAllSessions
0x180001e0e  mov     ebx, eax
0x180001e10  mov     [rsp+78h+var_58], eax
0x180001e14  cmp     eax, 80070057h
0x180001e19  jnz     short loc_180001E48
0x180001e1b  cmp     [rdi], r14d
0x180001e1e  jnb     short loc_180001E48
0x180001e20  lea     rcx, [rsp+78h+var_48]; unsigned __int16 *
0x180001e25  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180001e2a  mov     rcx, rax
0x180001e2d  lea     r9, [rsp+78h+arg_8]
0x180001e35  lea     r8, [rsp+78h+var_50]
0x180001e3a  mov     rdx, rdi
0x180001e3d  call    RpcGetAllSessions
0x180001e42  mov     ebx, eax
0x180001e44  mov     [rsp+78h+var_58], eax
0x180001e48  jmp     short loc_180001E83
0x180001e4a  mov     ebx, eax
0x180001e4c  test    eax, eax
0x180001e4e  jle     short loc_180001E59
0x180001e50  movzx   ebx, ax
0x180001e53  or      ebx, 80070000h
0x180001e59  mov     [rsp+78h+var_58], ebx
0x180001e5d  mov     r8d, ebx
0x180001e60  lea     rdx, aRpcgetallsessi_0; "RpcGetAllSessions threw an exception: 0"...
0x180001e67  mov     ecx, 8; int
0x180001e6c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001e71  xor     esi, esi
0x180001e73  mov     r15, [rsp+78h+arg_18]
0x180001e7b  mov     r12, [rsp+78h+arg_10]
0x180001e83  test    ebx, ebx
0x180001e85  jns     short loc_180001EA7
0x180001e87  lea     r9, aWinstationgeta_8; "_WinStationGetAllSessions"
0x180001e8e  mov     r8d, ebx
0x180001e91  lea     rdx, aRpcgetallsessi_1; "RpcGetAllSessions failed: 0x%x in %s"
0x180001e98  mov     ecx, 8; int
0x180001e9d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001ea2  jmp     loc_180001FEE
0x180001ea7  imul    eax, [rsp+78h+arg_8], 158h
0x180001eb2  mov     edi, eax
0x180001eb4  mov     edx, eax; uBytes
0x180001eb6  xor     ecx, ecx; uFlags
0x180001eb8  call    cs:__imp_LocalAlloc
0x180001ebf  nop     dword ptr [rax+rax+00h]
0x180001ec4  mov     r13, rax
0x180001ec7  test    rax, rax
0x180001eca  jnz     short loc_180001ED6
0x180001ecc  mov     ebx, 8007000Eh
0x180001ed1  jmp     loc_180001FEE
0x180001ed6  mov     rax, 0BE82FA0BE82FA0BFh
0x180001ee0  mul     rdi
0x180001ee3  mov     r14, rdx
0x180001ee6  shr     r14, 8
0x180001eea  cmp     [rsp+78h+arg_8], esi
0x180001ef1  jbe     loc_180001FE7
0x180001ef7  cmp     esi, r14d
0x180001efa  jnb     loc_180001FE7
0x180001f00  mov     ebx, esi
0x180001f02  imul    rdi, rbx, 158h
0x180001f09  add     rdi, r13
0x180001f0c  xor     edx, edx; Val
0x180001f0e  mov     r8d, 158h; Size
0x180001f14  mov     rcx, rdi; void *
0x180001f17  call    memset_0
0x180001f1c  imul    r11, rbx, 15Ch
0x180001f23  mov     rax, [rsp+78h+var_50]
0x180001f28  mov     ecx, [r11+rax+4]
0x180001f2d  mov     [rdi], ecx
0x180001f2f  mov     rax, [rsp+78h+var_50]
0x180001f34  mov     ecx, [r11+rax+50h]
0x180001f39  mov     [rdi+4Ch], ecx
0x180001f3c  mov     rax, [rsp+78h+var_50]
0x180001f41  mov     ecx, [r11+rax+8]
0x180001f46  mov     [rdi+4], ecx
0x180001f49  mov     r8, [rsp+78h+var_50]
0x180001f4e  add     r8, 0Ch
0x180001f52  add     r8, r11; unsigned __int16 *
0x180001f55  lea     rcx, [rdi+8]; unsigned __int16 *
0x180001f59  mov     edx, 20h ; ' '; unsigned __int64
0x180001f5e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001f63  mov     r8, [rsp+78h+var_50]
0x180001f68  add     r8, 54h ; 'T'
0x180001f6c  add     r8, r11; unsigned __int16 *
0x180001f6f  lea     rcx, [rdi+50h]; unsigned __int16 *
0x180001f73  mov     ebx, 21h ; '!'
0x180001f78  mov     edx, ebx; unsigned __int64
0x180001f7a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001f7f  mov     r8, [rsp+78h+var_50]
0x180001f84  add     r8, 96h
0x180001f8b  add     r8, r11; unsigned __int16 *
0x180001f8e  lea     rcx, [rdi+92h]; unsigned __int16 *
0x180001f95  mov     edx, ebx; unsigned __int64
0x180001f97  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001f9c  mov     r8, [rsp+78h+var_50]
0x180001fa1  add     r8, 0D8h
0x180001fa8  add     r8, r11; unsigned __int16 *
0x180001fab  lea     rcx, [rdi+0D4h]; unsigned __int16 *
0x180001fb2  mov     edx, ebx; unsigned __int64
0x180001fb4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001fb9  mov     r8, [rsp+78h+var_50]
0x180001fbe  add     r8, 11Ah
0x180001fc5  add     r8, r11; unsigned __int16 *
0x180001fc8  lea     rcx, [rdi+116h]; unsigned __int16 *
0x180001fcf  mov     edx, ebx; unsigned __int64
0x180001fd1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001fd6  mov     ebx, eax
0x180001fd8  inc     esi
0x180001fda  cmp     esi, [rsp+78h+arg_8]
0x180001fe1  jb      loc_180001EF7
0x180001fe7  mov     [r12], r13
0x180001feb  mov     [r15], r14d
0x180001fee  lea     rcx, [rsp+78h+var_48]; this
0x180001ff3  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180001ff8  mov     eax, ebx
0x180001ffa  add     rsp, 40h
0x180001ffe  pop     r15
0x180002000  pop     r14
0x180002002  pop     r13
0x180002004  pop     r12
0x180002006  pop     rdi
0x180002007  pop     rsi
0x180002008  pop     rbx
0x180002009  retn
0x180032dab  push    rbp
0x180032dad  sub     rsp, 20h
0x180032db1  mov     rbp, rdx
0x180032db4  mov     rcx, [rcx]
0x180032db7  mov     ecx, [rcx]; ExceptionCode
0x180032db9  call    cs:__imp_I_RpcExceptionFilter
0x180032dc0  nop     dword ptr [rax+rax+00h]
0x180032dc5  nop
0x180032dc6  add     rsp, 20h
0x180032dca  pop     rbp
0x180032dcb  retn
```
