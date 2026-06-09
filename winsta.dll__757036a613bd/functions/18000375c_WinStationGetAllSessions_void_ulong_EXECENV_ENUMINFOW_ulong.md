# _WinStationGetAllSessions(void *,ulong *,_EXECENV_ENUMINFOW * *,ulong *)

- ea: `0x18000375c`
- end: `0x1800039e0`
- name: `?_WinStationGetAllSessions@@YAJPEAXPEAKPEAPEAU_EXECENV_ENUMINFOW@@1@Z`
- size: `644`
- prototype: `__int64 __fastcall(void *, unsigned int *, struct _EXECENV_ENUMINFOW **, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180004bb0`
- `0x18002a460`

## callees

- `0x18000375c`
- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18000bcf0`
- `0x1800245e0`
- `0x18002fe06`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003894`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003894`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030044`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030044`

## string_xrefs

- `0x1800037b4`: `Failed to open binding`

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
0x18000375c  mov     rax, rsp
0x18000375f  mov     [rax+20h], r9
0x180003763  mov     [rax+18h], r8
0x180003767  push    rbx
0x180003768  push    rsi
0x180003769  push    rdi
0x18000376a  push    r12
0x18000376c  push    r13
0x18000376e  push    r14
0x180003770  push    r15
0x180003772  sub     rsp, 40h
0x180003776  mov     r15, r9
0x180003779  mov     r12, r8
0x18000377c  mov     rdi, rdx
0x18000377f  xor     esi, esi
0x180003781  mov     [rax+10h], esi
0x180003784  mov     [rax-50h], rsi
0x180003788  mov     r14d, [rdx]
0x18000378b  mov     [r8], rsi
0x18000378e  mov     [r9], esi
0x180003791  xor     r8d, r8d; int
0x180003794  mov     rdx, rcx; void *
0x180003797  lea     rcx, [rax-48h]; this
0x18000379b  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800037a0  lea     rcx, [rsp+78h+var_48]; unsigned __int16 *
0x1800037a5  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800037aa  test    rax, rax
0x1800037ad  jnz     short loc_1800037C8
0x1800037af  mov     ebx, 80004001h
0x1800037b4  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800037bb  lea     ecx, [rsi+8]; int
0x1800037be  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800037c3  jmp     loc_1800039C4
0x1800037c8  lea     rcx, [rsp+78h+var_48]; unsigned __int16 *
0x1800037cd  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800037d2  mov     rcx, rax
0x1800037d5  lea     r9, [rsp+78h+arg_8]
0x1800037dd  lea     r8, [rsp+78h+var_50]
0x1800037e2  mov     rdx, rdi
0x1800037e5  call    RpcGetAllSessions
0x1800037ea  mov     ebx, eax
0x1800037ec  mov     [rsp+78h+var_58], eax
0x1800037f0  cmp     eax, 80070057h
0x1800037f5  jnz     short loc_180003824
0x1800037f7  cmp     [rdi], r14d
0x1800037fa  jnb     short loc_180003824
0x1800037fc  lea     rcx, [rsp+78h+var_48]; unsigned __int16 *
0x180003801  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180003806  mov     rcx, rax
0x180003809  lea     r9, [rsp+78h+arg_8]
0x180003811  lea     r8, [rsp+78h+var_50]
0x180003816  mov     rdx, rdi
0x180003819  call    RpcGetAllSessions
0x18000381e  mov     ebx, eax
0x180003820  mov     [rsp+78h+var_58], eax
0x180003824  jmp     short loc_18000385F
0x180003826  mov     ebx, eax
0x180003828  test    eax, eax
0x18000382a  jle     short loc_180003835
0x18000382c  movzx   ebx, ax
0x18000382f  or      ebx, 80070000h
0x180003835  mov     [rsp+78h+var_58], ebx
0x180003839  mov     r8d, ebx
0x18000383c  lea     rdx, aRpcgetallsessi_0; "RpcGetAllSessions threw an exception: 0"...
0x180003843  mov     ecx, 8; int
0x180003848  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000384d  xor     esi, esi
0x18000384f  mov     r15, [rsp+78h+arg_18]
0x180003857  mov     r12, [rsp+78h+arg_10]
0x18000385f  test    ebx, ebx
0x180003861  jns     short loc_180003883
0x180003863  lea     r9, aWinstationgeta_8; "_WinStationGetAllSessions"
0x18000386a  mov     r8d, ebx
0x18000386d  lea     rdx, aRpcgetallsessi_1; "RpcGetAllSessions failed: 0x%x in %s"
0x180003874  mov     ecx, 8; int
0x180003879  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000387e  jmp     loc_1800039C4
0x180003883  imul    eax, [rsp+78h+arg_8], 158h
0x18000388e  mov     edi, eax
0x180003890  mov     edx, eax; uBytes
0x180003892  xor     ecx, ecx; uFlags
0x180003894  call    cs:__imp_LocalAlloc
0x18000389a  mov     r13, rax
0x18000389d  test    rax, rax
0x1800038a0  jnz     short loc_1800038AC
0x1800038a2  mov     ebx, 8007000Eh
0x1800038a7  jmp     loc_1800039C4
0x1800038ac  mov     rax, 0BE82FA0BE82FA0BFh
0x1800038b6  mul     rdi
0x1800038b9  mov     r14, rdx
0x1800038bc  shr     r14, 8
0x1800038c0  cmp     [rsp+78h+arg_8], esi
0x1800038c7  jbe     loc_1800039BD
0x1800038cd  cmp     esi, r14d
0x1800038d0  jnb     loc_1800039BD
0x1800038d6  mov     ebx, esi
0x1800038d8  imul    rdi, rbx, 158h
0x1800038df  add     rdi, r13
0x1800038e2  xor     edx, edx; Val
0x1800038e4  mov     r8d, 158h; Size
0x1800038ea  mov     rcx, rdi; void *
0x1800038ed  call    memset_0
0x1800038f2  imul    r11, rbx, 15Ch
0x1800038f9  mov     rax, [rsp+78h+var_50]
0x1800038fe  mov     ecx, [r11+rax+4]
0x180003903  mov     [rdi], ecx
0x180003905  mov     rax, [rsp+78h+var_50]
0x18000390a  mov     ecx, [r11+rax+50h]
0x18000390f  mov     [rdi+4Ch], ecx
0x180003912  mov     rax, [rsp+78h+var_50]
0x180003917  mov     ecx, [r11+rax+8]
0x18000391c  mov     [rdi+4], ecx
0x18000391f  mov     r8, [rsp+78h+var_50]
0x180003924  add     r8, 0Ch
0x180003928  add     r8, r11; unsigned __int16 *
0x18000392b  lea     rcx, [rdi+8]; unsigned __int16 *
0x18000392f  mov     edx, 20h ; ' '; unsigned __int64
0x180003934  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003939  mov     r8, [rsp+78h+var_50]
0x18000393e  add     r8, 54h ; 'T'
0x180003942  add     r8, r11; unsigned __int16 *
0x180003945  lea     rcx, [rdi+50h]; unsigned __int16 *
0x180003949  mov     ebx, 21h ; '!'
0x18000394e  mov     edx, ebx; unsigned __int64
0x180003950  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003955  mov     r8, [rsp+78h+var_50]
0x18000395a  add     r8, 96h
0x180003961  add     r8, r11; unsigned __int16 *
0x180003964  lea     rcx, [rdi+92h]; unsigned __int16 *
0x18000396b  mov     edx, ebx; unsigned __int64
0x18000396d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003972  mov     r8, [rsp+78h+var_50]
0x180003977  add     r8, 0D8h
0x18000397e  add     r8, r11; unsigned __int16 *
0x180003981  lea     rcx, [rdi+0D4h]; unsigned __int16 *
0x180003988  mov     edx, ebx; unsigned __int64
0x18000398a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000398f  mov     r8, [rsp+78h+var_50]
0x180003994  add     r8, 11Ah
0x18000399b  add     r8, r11; unsigned __int16 *
0x18000399e  lea     rcx, [rdi+116h]; unsigned __int16 *
0x1800039a5  mov     edx, ebx; unsigned __int64
0x1800039a7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800039ac  mov     ebx, eax
0x1800039ae  inc     esi
0x1800039b0  cmp     esi, [rsp+78h+arg_8]
0x1800039b7  jb      loc_1800038CD
0x1800039bd  mov     [r12], r13
0x1800039c1  mov     [r15], r14d
0x1800039c4  lea     rcx, [rsp+78h+var_48]; this
0x1800039c9  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800039ce  mov     eax, ebx
0x1800039d0  add     rsp, 40h
0x1800039d4  pop     r15
0x1800039d6  pop     r14
0x1800039d8  pop     r13
0x1800039da  pop     r12
0x1800039dc  pop     rdi
0x1800039dd  pop     rsi
0x1800039de  pop     rbx
0x1800039df  retn
0x180030036  push    rbp
0x180030038  sub     rsp, 20h
0x18003003c  mov     rbp, rdx
0x18003003f  mov     rcx, [rcx]
0x180030042  mov     ecx, [rcx]; ExceptionCode
0x180030044  call    cs:__imp_I_RpcExceptionFilter
0x18003004a  nop
0x18003004b  add     rsp, 20h
0x18003004f  pop     rbp
0x180030050  retn
```
