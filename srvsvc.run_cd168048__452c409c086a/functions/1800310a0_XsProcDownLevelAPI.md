# XsProcDownLevelAPI

- ea: `0x1800310a0`
- end: `0x180031324`
- name: `XsProcDownLevelAPI`
- size: `644`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020dc0`
- `0x180020de8`
- `0x1800301d4`
- `0x1800310a0`
- `0x180041fe0`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180031123`
- `ntdll!RtlAcquireResourceShared` at `0x180031123`
- `ntdll!RtlReleaseResource` at `0x1800312c0`
- `ntdll!RtlReleaseResource` at `0x1800312c0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800312d2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800312d2`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800310cc`
- `RPCRT4!RpcAsyncAbortCall` at `0x180031310`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800310cc`
- `RPCRT4!RpcAsyncAbortCall` at `0x180031310`
- `RPCRT4!RpcServerTestCancel` at `0x1800310ba`
- `RPCRT4!RpcServerTestCancel` at `0x1800310ba`

## pseudocode

```c
unsigned int __fastcall XsProcDownLevelAPI(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a3,
        unsigned int *a4)
{
  unsigned int result; // eax
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // esi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // eax

  if ( !RpcServerTestCancel(BindingHandle) )
  {
    result = RpcAsyncAbortCall(pAsync, 0x71Au);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        return WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 41,
                 WPP_961f2129f327316bc578c2fdd21cc406_Traceguids,
                 result);
    }
    return result;
  }
  RtlAcquireResourceShared(&stru_18005E3D8, 1u);
  if ( !dword_18005E43C )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
    }
    v10 = -1073741790;
    goto LABEL_28;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DSDsDSDqDDqDqDqDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v9,
      *(_DWORD *)a3,
      *(_QWORD *)(a3 + 8),
      *(_DWORD *)(a3 + 4),
      *(_QWORD *)(a3 + 24),
      *(_DWORD *)(a3 + 16),
      *(_QWORD *)(a3 + 40),
      *(_DWORD *)(a3 + 32),
      *(_QWORD *)(a3 + 56),
      *(_DWORD *)(a3 + 48),
      *(_DWORD *)(a3 + 64),
      *(_QWORD *)(a3 + 72),
      *(_DWORD *)(a3 + 68),
      *(_QWORD *)(a3 + 88),
      *(_DWORD *)(a3 + 80),
      *(_QWORD *)(a3 + 104),
      *(_DWORD *)(a3 + 96),
      *(_DWORD *)(a3 + 112),
      *(_DWORD *)(a3 + 116),
      *(_DWORD *)(a3 + 120));
    v11 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)a3 == 104 || *(_DWORD *)a3 == 215 )
  {
    v14 = XsProcessNetServerEnumRapRequest(a3, (unsigned int)(*(_DWORD *)a3 - 104));
    v10 = v14;
    if ( v14 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v12 = 44;
        v13 = (unsigned int)v14;
        goto LABEL_27;
      }
    }
  }
  else
  {
    v10 = -1073741796;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x10) != 0 && *((_BYTE *)v11 + 25) )
    {
      v12 = 45;
      v13 = 3221225500LL;
LABEL_27:
      WPP_SF_d(v11[2], v12, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, v13);
    }
  }
LABEL_28:
  RtlReleaseResource(&stru_18005E3D8);
  *a4 = v10;
  if ( !v10 )
    return RpcAsyncCompleteCall(pAsync, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, v10);
  }
  return RpcAsyncAbortCall(pAsync, *a4);
}

```

## disassembly

```asm
0x1800310a0  push    rbx
0x1800310a2  push    rsi
0x1800310a3  push    r14
0x1800310a5  push    r15
0x1800310a7  sub     rsp, 0B8h
0x1800310ae  mov     r14, rcx
0x1800310b1  mov     r15, r9
0x1800310b4  mov     rcx, rdx; BindingHandle
0x1800310b7  mov     rsi, r8
0x1800310ba  call    cs:__imp_RpcServerTestCancel
0x1800310c0  test    eax, eax
0x1800310c2  jnz     short loc_18003111A
0x1800310c4  mov     edx, 71Ah; ExceptionCode
0x1800310c9  mov     rcx, r14; pAsync
0x1800310cc  call    cs:__imp_RpcAsyncAbortCall
0x1800310d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800310d9  lea     rbx, WPP_GLOBAL_Control
0x1800310e0  cmp     rcx, rbx
0x1800310e3  jz      loc_180031316
0x1800310e9  test    byte ptr [rcx+1Ch], 10h
0x1800310ed  jz      loc_180031316
0x1800310f3  cmp     byte ptr [rcx+19h], 1
0x1800310f7  jb      loc_180031316
0x1800310fd  mov     rcx, [rcx+10h]
0x180031101  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180031108  mov     edx, 29h ; ')'
0x18003110d  mov     r9d, eax
0x180031110  call    WPP_SF_d
0x180031115  jmp     loc_180031316
0x18003111a  mov     dl, 1; Wait
0x18003111c  lea     rcx, stru_18005E3D8; Resource
0x180031123  call    cs:__imp_RtlAcquireResourceShared
0x180031129  cmp     cs:dword_18005E43C, 0
0x180031130  jnz     short loc_180031170
0x180031132  mov     rcx, cs:WPP_GLOBAL_Control
0x180031139  lea     rbx, WPP_GLOBAL_Control
0x180031140  cmp     rcx, rbx
0x180031143  jz      short loc_180031166
0x180031145  test    byte ptr [rcx+1Ch], 10h
0x180031149  jz      short loc_180031166
0x18003114b  cmp     byte ptr [rcx+19h], 1
0x18003114f  jb      short loc_180031166
0x180031151  mov     rcx, [rcx+10h]
0x180031155  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x18003115c  mov     edx, 2Ah ; '*'
0x180031161  call    WPP_SF_
0x180031166  mov     esi, 0C0000022h
0x18003116b  jmp     loc_1800312B9
0x180031170  mov     rcx, cs:WPP_GLOBAL_Control
0x180031177  lea     rbx, WPP_GLOBAL_Control
0x18003117e  cmp     rcx, rbx
0x180031181  jz      loc_18003124C
0x180031187  test    byte ptr [rcx+1Ch], 10h
0x18003118b  jz      loc_18003124C
0x180031191  cmp     byte ptr [rcx+19h], 2
0x180031195  jb      loc_18003124C
0x18003119b  mov     eax, [rsi+78h]
0x18003119e  mov     [rsp+0D8h+var_30], eax
0x1800311a5  mov     eax, [rsi+74h]
0x1800311a8  mov     [rsp+0D8h+var_38], eax
0x1800311af  mov     eax, [rsi+70h]
0x1800311b2  mov     r9d, [rsi]
0x1800311b5  mov     rcx, [rcx+10h]
0x1800311b9  mov     [rsp+0D8h+var_40], eax
0x1800311c0  mov     eax, [rsi+60h]
0x1800311c3  mov     [rsp+0D8h+var_48], eax
0x1800311ca  mov     rax, [rsi+68h]
0x1800311ce  mov     [rsp+0D8h+var_50], rax
0x1800311d6  mov     eax, [rsi+50h]
0x1800311d9  mov     [rsp+0D8h+var_58], eax
0x1800311e0  mov     rax, [rsi+58h]
0x1800311e4  mov     [rsp+0D8h+var_60], rax
0x1800311e9  mov     eax, [rsi+44h]
0x1800311ec  mov     [rsp+0D8h+var_68], eax
0x1800311f0  mov     rax, [rsi+48h]
0x1800311f4  mov     [rsp+0D8h+var_70], rax
0x1800311f9  mov     eax, [rsi+40h]
0x1800311fc  mov     [rsp+0D8h+var_78], eax
0x180031200  mov     eax, [rsi+30h]
0x180031203  mov     [rsp+0D8h+var_80], eax
0x180031207  mov     rax, [rsi+38h]
0x18003120b  mov     [rsp+0D8h+var_88], rax
0x180031210  mov     eax, [rsi+20h]
0x180031213  mov     [rsp+0D8h+var_90], eax
0x180031217  mov     rax, [rsi+28h]
0x18003121b  mov     [rsp+0D8h+var_98], rax
0x180031220  mov     eax, [rsi+10h]
0x180031223  mov     [rsp+0D8h+var_A0], eax
0x180031227  mov     rax, [rsi+18h]
0x18003122b  mov     [rsp+0D8h+var_A8], rax
0x180031230  mov     eax, [rsi+4]
0x180031233  mov     [rsp+0D8h+var_B0], eax
0x180031237  mov     rax, [rsi+8]
0x18003123b  mov     [rsp+0D8h+var_B8], rax
0x180031240  call    WPP_SF_DSDsDSDqDDqDqDqDDDD
0x180031245  mov     rcx, cs:WPP_GLOBAL_Control
0x18003124c  mov     edx, [rsi]
0x18003124e  sub     edx, 68h ; 'h'
0x180031251  jz      short loc_18003127B
0x180031253  cmp     edx, 6Fh ; 'o'
0x180031256  jz      short loc_18003127B
0x180031258  mov     esi, 0C000001Ch
0x18003125d  cmp     rcx, rbx
0x180031260  jz      short loc_1800312B9
0x180031262  test    byte ptr [rcx+1Ch], 10h
0x180031266  jz      short loc_1800312B9
0x180031268  cmp     byte ptr [rcx+19h], 1
0x18003126c  jb      short loc_1800312B9
0x18003126e  mov     edx, 2Dh ; '-'
0x180031273  mov     r9d, 0C000001Ch
0x180031279  jmp     short loc_1800312A9
0x18003127b  mov     rcx, rsi
0x18003127e  call    XsProcessNetServerEnumRapRequest
0x180031283  mov     esi, eax
0x180031285  test    eax, eax
0x180031287  jns     short loc_1800312B9
0x180031289  mov     rcx, cs:WPP_GLOBAL_Control
0x180031290  cmp     rcx, rbx
0x180031293  jz      short loc_1800312B9
0x180031295  test    byte ptr [rcx+1Ch], 10h
0x180031299  jz      short loc_1800312B9
0x18003129b  cmp     byte ptr [rcx+19h], 1
0x18003129f  jb      short loc_1800312B9
0x1800312a1  mov     edx, 2Ch ; ','
0x1800312a6  mov     r9d, eax
0x1800312a9  mov     rcx, [rcx+10h]
0x1800312ad  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800312b4  call    WPP_SF_d
0x1800312b9  lea     rcx, stru_18005E3D8; Resource
0x1800312c0  call    cs:__imp_RtlReleaseResource
0x1800312c6  mov     [r15], esi
0x1800312c9  test    esi, esi
0x1800312cb  jnz     short loc_1800312DA
0x1800312cd  xor     edx, edx; Reply
0x1800312cf  mov     rcx, r14; pAsync
0x1800312d2  call    cs:__imp_RpcAsyncCompleteCall
0x1800312d8  jmp     short loc_180031316
0x1800312da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312e1  cmp     rcx, rbx
0x1800312e4  jz      short loc_18003130A
0x1800312e6  test    byte ptr [rcx+1Ch], 10h
0x1800312ea  jz      short loc_18003130A
0x1800312ec  cmp     byte ptr [rcx+19h], 1
0x1800312f0  jb      short loc_18003130A
0x1800312f2  mov     rcx, [rcx+10h]
0x1800312f6  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800312fd  mov     edx, 2Eh ; '.'
0x180031302  mov     r9d, esi
0x180031305  call    WPP_SF_d
0x18003130a  mov     edx, [r15]; ExceptionCode
0x18003130d  mov     rcx, r14; pAsync
0x180031310  call    cs:__imp_RpcAsyncAbortCall
0x180031316  add     rsp, 0B8h
0x18003131d  pop     r15
0x18003131f  pop     r14
0x180031321  pop     rsi
0x180031322  pop     rbx
0x180031323  retn
```
