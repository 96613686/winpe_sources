# CByteStream::CopyTo(IWerByteStream *,void *)

- ea: `0x1800137d0`
- end: `0x1800139b3`
- name: `?CopyTo@CByteStream@@UEAAJPEAUIWerByteStream@@PEAX@Z`
- size: `483`
- prototype: `__int64 __fastcall(CByteStream *__hidden this, struct IWerByteStream *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180011ef8`
- `0x1800137d0`
- `0x180013df4`
- `0x1800344f0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800138a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800138a1`

## pseudocode

```c
__int64 __fastcall CByteStream::CopyTo(CByteStream *this, struct IWerByteStream *a2, void *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned __int64 i; // rdi
  __int64 v12; // rax
  unsigned int v14; // [rsp+30h] [rbp-1048h] BYREF
  _DWORD v15[3]; // [rsp+34h] [rbp-1044h] BYREF
  _BYTE v16[4096]; // [rsp+40h] [rbp-1038h] BYREF

  v14 = 0;
  v15[0] = 0;
  memset_0(v16, 0, sizeof(v16));
  v6 = (*(__int64 (__fastcall **)(CByteStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 16LL))(this, 0, 0, 0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    for ( i = 0; ; i += v12 )
    {
      if ( i >= (*(__int64 (__fastcall **)(CByteStream *))(*(_QWORD *)this + 32LL))(this) )
        return 0;
      if ( a3 && !WaitForSingleObject(a3, 0) )
      {
        v7 = -2147467260;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v9 = 11;
          v10 = 2147500036LL;
          goto LABEL_6;
        }
        return v7;
      }
      v6 = (**(__int64 (__fastcall ***)(CByteStream *, _BYTE *, __int64, unsigned int *, void *))this)(
             this,
             v16,
             4096,
             &v14,
             a3);
      v7 = v6;
      if ( v6 < 0 )
        break;
      v6 = (*(__int64 (__fastcall **)(struct IWerByteStream *, _BYTE *, _QWORD, _DWORD *, void *))(*(_QWORD *)a2 + 8LL))(
             a2,
             v16,
             v14,
             v15,
             a3);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 13;
          goto LABEL_5;
        }
        return v7;
      }
      v12 = v14;
      if ( v14 != v15[0] )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v12 = v14;
      }
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 12;
      goto LABEL_5;
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 10;
LABEL_5:
      v10 = (unsigned int)v6;
LABEL_6:
      WPP_SF_d(v8[2], v9, &WPP_7066dd0f05d133a0820bef218904ca03_Traceguids, v10);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800137d0  push    rbx
0x1800137d2  push    rsi
0x1800137d3  push    rdi
0x1800137d4  push    r14
0x1800137d6  push    r15
0x1800137d8  mov     eax, 1050h
0x1800137dd  call    _alloca_probe
0x1800137e2  sub     rsp, rax
0x1800137e5  mov     rax, cs:__security_cookie
0x1800137ec  xor     rax, rsp
0x1800137ef  mov     [rsp+1078h+var_38], rax
0x1800137f7  mov     rsi, r8
0x1800137fa  mov     [rsp+1078h+var_1048], 0
0x180013802  mov     r15, rdx
0x180013805  mov     [rsp+1078h+var_1044], 0
0x18001380d  mov     r14, rcx
0x180013810  xor     edx, edx; Val
0x180013812  mov     r8d, 1000h; Size
0x180013818  lea     rcx, [rsp+1078h+var_1038]; void *
0x18001381d  call    memset_0
0x180013822  mov     rax, [r14]
0x180013825  xor     r9d, r9d
0x180013828  xor     r8d, r8d
0x18001382b  xor     edx, edx
0x18001382d  mov     rcx, r14
0x180013830  mov     rax, [rax+10h]
0x180013834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013839  mov     ebx, eax
0x18001383b  test    eax, eax
0x18001383d  jns     short loc_18001387D
0x18001383f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013846  lea     rdx, WPP_GLOBAL_Control
0x18001384d  cmp     rcx, rdx
0x180013850  jz      loc_180013992
0x180013856  test    byte ptr [rcx+1Ch], 1
0x18001385a  jz      loc_180013992
0x180013860  mov     edx, 0Ah
0x180013865  mov     r9d, eax
0x180013868  mov     rcx, [rcx+10h]
0x18001386c  lea     r8, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids
0x180013873  call    WPP_SF_d
0x180013878  jmp     loc_180013992
0x18001387d  xor     edi, edi
0x18001387f  mov     rax, [r14]
0x180013882  mov     rcx, r14
0x180013885  mov     rax, [rax+20h]
0x180013889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001388e  cmp     rdi, rax
0x180013891  jnb     loc_180013990
0x180013897  test    rsi, rsi
0x18001389a  jz      short loc_1800138AB
0x18001389c  xor     edx, edx; dwMilliseconds
0x18001389e  mov     rcx, rsi; hHandle
0x1800138a1  call    cs:__imp_WaitForSingleObject
0x1800138a7  test    eax, eax
0x1800138a9  jz      short loc_18001391C
0x1800138ab  mov     rax, [r14]
0x1800138ae  lea     r9, [rsp+1078h+var_1048]
0x1800138b3  mov     r8d, 1000h
0x1800138b9  mov     [rsp+1078h+var_1058], rsi
0x1800138be  lea     rdx, [rsp+1078h+var_1038]
0x1800138c3  mov     rcx, r14
0x1800138c6  mov     rax, [rax]
0x1800138c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138ce  mov     ebx, eax
0x1800138d0  test    eax, eax
0x1800138d2  js      loc_18001396D
0x1800138d8  mov     rax, [r15]
0x1800138db  lea     r9, [rsp+1078h+var_1044]
0x1800138e0  mov     r8d, [rsp+1078h+var_1048]
0x1800138e5  lea     rdx, [rsp+1078h+var_1038]
0x1800138ea  mov     rcx, r15
0x1800138ed  mov     [rsp+1078h+var_1058], rsi
0x1800138f2  mov     rax, [rax+8]
0x1800138f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138fb  mov     ebx, eax
0x1800138fd  test    eax, eax
0x1800138ff  js      short loc_18001394A
0x180013901  mov     eax, [rsp+1078h+var_1048]
0x180013905  cmp     eax, [rsp+1078h+var_1044]
0x180013909  jz      short loc_180013914
0x18001390b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013910  mov     eax, [rsp+1078h+var_1048]
0x180013914  add     rdi, rax
0x180013917  jmp     loc_18001387F
0x18001391c  mov     ebx, 80004004h
0x180013921  mov     rcx, cs:WPP_GLOBAL_Control
0x180013928  lea     rdx, WPP_GLOBAL_Control
0x18001392f  cmp     rcx, rdx
0x180013932  jz      short loc_180013992
0x180013934  test    byte ptr [rcx+1Ch], 4
0x180013938  jz      short loc_180013992
0x18001393a  mov     edx, 0Bh
0x18001393f  mov     r9d, 80004004h
0x180013945  jmp     loc_180013868
0x18001394a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013951  lea     rdx, WPP_GLOBAL_Control
0x180013958  cmp     rcx, rdx
0x18001395b  jz      short loc_180013992
0x18001395d  test    byte ptr [rcx+1Ch], 1
0x180013961  jz      short loc_180013992
0x180013963  mov     edx, 0Dh
0x180013968  jmp     loc_180013865
0x18001396d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013974  lea     rdx, WPP_GLOBAL_Control
0x18001397b  cmp     rcx, rdx
0x18001397e  jz      short loc_180013992
0x180013980  test    byte ptr [rcx+1Ch], 1
0x180013984  jz      short loc_180013992
0x180013986  mov     edx, 0Ch
0x18001398b  jmp     loc_180013865
0x180013990  xor     ebx, ebx
0x180013992  mov     eax, ebx
0x180013994  mov     rcx, [rsp+1078h+var_38]
0x18001399c  xor     rcx, rsp; StackCookie
0x18001399f  call    __security_check_cookie
0x1800139a4  add     rsp, 1050h
0x1800139ab  pop     r15
0x1800139ad  pop     r14
0x1800139af  pop     rdi
0x1800139b0  pop     rsi
0x1800139b1  pop     rbx
0x1800139b2  retn
```
