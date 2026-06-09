# WFDSvcLowPrivOpenAdvertiserSessionLib(void *,ulong,uchar (*)[6],ulong,void * *)

- ea: `0x180059278`
- end: `0x180059552`
- name: `?WFDSvcLowPrivOpenAdvertiserSessionLib@@YAKPEAXKPEAY05EKPEAPEAX@Z`
- size: `730`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, unsigned int@<edx>, unsigned __int8 (*)[6]@<r8>, unsigned int@<r9d>, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18002d290`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x1800132cc`
- `0x180043d68`
- `0x18004fe34`
- `0x18004ffb8`
- `0x180059278`
- `0x18005ab64`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18005941b`
- `RPCRT4!NdrClientCall3` at `0x18005941b`

## pseudocode

```c
__int64 __fastcall WFDSvcLowPrivOpenAdvertiserSessionLib(void *a1, int a2, unsigned __int8 (*a3)[6], int a4, void **a5)
{
  union DOT11_OUI_HEADER *v9; // r10
  void **v10; // r14
  unsigned int v11; // edi
  __int64 v12; // rdx
  struct _WFD_API_ASYNC_CONTEXT *v13; // rbx
  struct _WFD_API_ASYNC_CONTEXT *v14; // rbx
  __int64 v16; // [rsp+20h] [rbp-58h]
  unsigned int Pointer; // [rsp+40h] [rbp-38h]
  struct _WFD_API_ASYNC_CONTEXT *v18; // [rsp+80h] [rbp+8h] BYREF

  v18 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 404, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( a1 && a3 && (v10 = a5) != 0 )
  {
    if ( v9 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v9 + 105) >= 3u
      && (*((_DWORD *)v9 + 27) & 0x1000) != 0 )
    {
      WPP_SF__MAC_D(*((_QWORD *)v9 + 12), 406, (unsigned __int8 *)a3, (unsigned __int8 *)a3, a4);
    }
    v11 = LocalWfdAsyncContextCreateInternal(a1, &v18, 1);
    if ( v11 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
      {
        v12 = 407;
LABEL_27:
        WPP_SF_(*((_QWORD *)v9 + 12), v12, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
        goto LABEL_28;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
      {
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          408,
          WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids,
          *((_QWORD *)v18 + 2));
      }
      v13 = v18;
      *(_DWORD *)v18 = 8;
      *((_DWORD *)v13 + 40) = *(_DWORD *)a3;
      *((_WORD *)v13 + 82) = *(_WORD *)&(*a3)[4];
      *((_DWORD *)v13 + 42) = a4;
      LODWORD(v16) = a2;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&winwlan_lowpriv_ProxyInfo,
                                0x1Bu,
                                0,
                                **((_QWORD **)v13 + 1),
                                v16,
                                (char *)v13 + 160,
                                a4,
                                (char *)v13 + 152).Pointer;
      v11 = ServiceStatus(Pointer);
      if ( !v11 )
      {
        v14 = v18;
        LocalWfdAsyncContextPendingMarkIdle(v18);
        *v10 = (void *)*((_QWORD *)v14 + 2);
LABEL_28:
        v9 = WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v11 = 87;
    if ( v9 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v9 + 105)
      && (*((_DWORD *)v9 + 27) & 0x1000) != 0 )
    {
      v12 = 405;
      goto LABEL_27;
    }
  }
  if ( v11 && v18 )
  {
    LocalWfdAsyncContextDeref(v18);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v9 + 105) >= 4u
    && (*((_BYTE *)v9 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v9 + 12), 410, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180059278  mov     rax, rsp
0x18005927b  mov     [rax+10h], rbx
0x18005927f  mov     [rax+18h], rsi
0x180059283  push    rdi
0x180059284  push    r12
0x180059286  push    r13
0x180059288  push    r14
0x18005928a  push    r15
0x18005928c  sub     rsp, 50h
0x180059290  mov     r12d, r9d
0x180059293  mov     r15, r8
0x180059296  mov     r13d, edx
0x180059299  mov     rbx, rcx
0x18005929c  mov     qword ptr [rax+8], 0
0x1800592a4  lea     rsi, WPP_GLOBAL_Control
0x1800592ab  mov     r10, cs:WPP_GLOBAL_Control
0x1800592b2  cmp     r10, rsi
0x1800592b5  jz      short loc_1800592E1
0x1800592b7  cmp     byte ptr [r10+69h], 4
0x1800592bc  jb      short loc_1800592E1
0x1800592be  test    byte ptr [r10+6Ch], 2
0x1800592c3  jz      short loc_1800592E1
0x1800592c5  mov     edx, 194h
0x1800592ca  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800592d1  mov     rcx, [r10+60h]
0x1800592d5  call    WPP_SF_
0x1800592da  mov     r10, cs:WPP_GLOBAL_Control
0x1800592e1  test    rbx, rbx
0x1800592e4  jz      loc_1800594B4
0x1800592ea  test    r15, r15
0x1800592ed  jz      loc_1800594B4
0x1800592f3  mov     r14, [rsp+78h+arg_20]
0x1800592fb  test    r14, r14
0x1800592fe  jz      loc_1800594B4
0x180059304  cmp     r10, rsi
0x180059307  jz      short loc_180059330
0x180059309  cmp     byte ptr [r10+69h], 3
0x18005930e  jb      short loc_180059330
0x180059310  test    dword ptr [r10+6Ch], 1000h
0x180059318  jz      short loc_180059330
0x18005931a  mov     edx, 196h
0x18005931f  mov     dword ptr [rsp+78h+var_58], r12d
0x180059324  mov     r9, r15
0x180059327  mov     rcx, [r10+60h]
0x18005932b  call    WPP_SF__MAC_D
0x180059330  mov     r8d, 1; int
0x180059336  lea     rdx, [rsp+78h+arg_0]; struct _WFD_API_ASYNC_CONTEXT **
0x18005933e  mov     rcx, rbx; void *
0x180059341  call    ?LocalWfdAsyncContextCreateInternal@@YAKPEAXPEAPEAU_WFD_API_ASYNC_CONTEXT@@H@Z; LocalWfdAsyncContextCreateInternal(void *,_WFD_API_ASYNC_CONTEXT * *,int)
0x180059346  mov     edi, eax
0x180059348  test    eax, eax
0x18005934a  jz      short loc_18005937F
0x18005934c  mov     r10, cs:WPP_GLOBAL_Control
0x180059353  cmp     r10, rsi
0x180059356  jz      loc_1800594EB
0x18005935c  cmp     byte ptr [r10+69h], 1
0x180059361  jb      loc_1800594EB
0x180059367  test    dword ptr [r10+6Ch], 1000h
0x18005936f  jz      loc_1800594EB
0x180059375  mov     edx, 197h
0x18005937a  jmp     loc_1800594D4
0x18005937f  mov     rcx, cs:WPP_GLOBAL_Control
0x180059386  cmp     rcx, rsi
0x180059389  jz      short loc_1800593BB
0x18005938b  cmp     byte ptr [rcx+69h], 3
0x18005938f  jb      short loc_1800593BB
0x180059391  test    dword ptr [rcx+6Ch], 1000h
0x180059398  jz      short loc_1800593BB
0x18005939a  mov     edx, 198h
0x18005939f  mov     r9, [rsp+78h+arg_0]
0x1800593a7  mov     r9, [r9+10h]
0x1800593ab  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800593b2  mov     rcx, [rcx+60h]
0x1800593b6  call    WPP_SF_q
0x1800593bb  mov     rbx, [rsp+78h+arg_0]
0x1800593c3  mov     dword ptr [rbx], 8
0x1800593c9  lea     rdx, [rbx+98h]
0x1800593d0  lea     rcx, [rdx+8]
0x1800593d4  mov     eax, [r15]
0x1800593d7  mov     [rcx], eax
0x1800593d9  movzx   eax, word ptr [r15+4]
0x1800593de  mov     [rcx+4], ax
0x1800593e2  mov     [rbx+0A8h], r12d
0x1800593e9  mov     rax, [rbx+8]
0x1800593ed  mov     [rsp+78h+var_30], 0
0x1800593f6  mov     [rsp+78h+var_40], rdx
0x1800593fb  mov     [rsp+78h+var_48], r12d
0x180059400  mov     [rsp+78h+var_50], rcx
0x180059405  mov     dword ptr [rsp+78h+var_58], r13d
0x18005940a  mov     r9, [rax]
0x18005940d  xor     r8d, r8d; pReturnValue
0x180059410  lea     edx, [r8+1Bh]; nProcNum
0x180059414  lea     rcx, ?winwlan_lowpriv_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18005941b  call    cs:__imp_NdrClientCall3
0x180059421  mov     rbx, rax
0x180059424  mov     [rsp+78h+var_30], rax
0x180059429  mov     [rsp+78h+var_38], eax
0x18005942d  mov     r10, cs:WPP_GLOBAL_Control
0x180059434  jmp     short loc_18005948E
0x180059436  mov     ebx, eax
0x180059438  mov     [rsp+78h+var_38], eax
0x18005943c  lea     rcx, WPP_GLOBAL_Control
0x180059443  mov     r10, cs:WPP_GLOBAL_Control
0x18005944a  cmp     r10, rcx
0x18005944d  jz      short loc_18005947F
0x18005944f  cmp     byte ptr [r10+69h], 1
0x180059454  jb      short loc_18005947F
0x180059456  test    dword ptr [r10+6Ch], 1000h
0x18005945e  jz      short loc_18005947F
0x180059460  mov     edx, 199h
0x180059465  mov     r9d, eax
0x180059468  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005946f  mov     rcx, [r10+60h]
0x180059473  call    WPP_SF_d
0x180059478  mov     r10, cs:WPP_GLOBAL_Control
0x18005947f  lea     rsi, WPP_GLOBAL_Control
0x180059486  mov     r14, [rsp+78h+arg_20]
0x18005948e  mov     ecx, ebx; unsigned int
0x180059490  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180059495  mov     edi, eax
0x180059497  test    eax, eax
0x180059499  jnz     short loc_1800594EB
0x18005949b  mov     rbx, [rsp+78h+arg_0]
0x1800594a3  mov     rcx, rbx; struct _WFD_API_ASYNC_CONTEXT *
0x1800594a6  call    ?LocalWfdAsyncContextPendingMarkIdle@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextPendingMarkIdle(_WFD_API_ASYNC_CONTEXT *)
0x1800594ab  mov     rax, [rbx+10h]
0x1800594af  mov     [r14], rax
0x1800594b2  jmp     short loc_1800594E4
0x1800594b4  mov     edi, 57h ; 'W'
0x1800594b9  cmp     r10, rsi
0x1800594bc  jz      short loc_1800594EB
0x1800594be  cmp     byte ptr [r10+69h], 1
0x1800594c3  jb      short loc_1800594EB
0x1800594c5  test    dword ptr [r10+6Ch], 1000h
0x1800594cd  jz      short loc_1800594EB
0x1800594cf  mov     edx, 195h
0x1800594d4  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800594db  mov     rcx, [r10+60h]
0x1800594df  call    WPP_SF_
0x1800594e4  mov     r10, cs:WPP_GLOBAL_Control
0x1800594eb  test    edi, edi
0x1800594ed  jz      short loc_18005950B
0x1800594ef  mov     rbx, [rsp+78h+arg_0]
0x1800594f7  test    rbx, rbx
0x1800594fa  jz      short loc_18005950B
0x1800594fc  mov     rcx, rbx; struct _WFD_API_ASYNC_CONTEXT *
0x1800594ff  call    ?LocalWfdAsyncContextDeref@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextDeref(_WFD_API_ASYNC_CONTEXT *)
0x180059504  mov     r10, cs:WPP_GLOBAL_Control
0x18005950b  cmp     r10, rsi
0x18005950e  jz      short loc_180059536
0x180059510  cmp     byte ptr [r10+69h], 4
0x180059515  jb      short loc_180059536
0x180059517  test    byte ptr [r10+6Ch], 2
0x18005951c  jz      short loc_180059536
0x18005951e  mov     edx, 19Ah
0x180059523  mov     r9d, edi
0x180059526  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005952d  mov     rcx, [r10+60h]
0x180059531  call    WPP_SF_d
0x180059536  mov     eax, edi
0x180059538  lea     r11, [rsp+78h+var_28]
0x18005953d  mov     rbx, [r11+38h]
0x180059541  mov     rsi, [r11+40h]
0x180059545  mov     rsp, r11
0x180059548  pop     r15
0x18005954a  pop     r14
0x18005954c  pop     r13
0x18005954e  pop     r12
0x180059550  pop     rdi
0x180059551  retn
0x180060bba  push    rbp
0x180060bbc  sub     rsp, 40h
0x180060bc0  mov     rbp, rdx
0x180060bc3  mov     rcx, [rcx]
0x180060bc6  mov     ecx, [rcx]; ExceptionCode
0x180060bc8  call    cs:__imp_RpcExceptionFilter
0x180060bce  nop
0x180060bcf  add     rsp, 40h
0x180060bd3  pop     rbp
0x180060bd4  retn
```
