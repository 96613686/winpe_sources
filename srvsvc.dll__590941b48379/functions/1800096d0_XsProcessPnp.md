# XsProcessPnp

- ea: `0x1800096d0`
- end: `0x1800098bb`
- name: `XsProcessPnp`
- size: `491`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009470`
- `0x1800096d0`
- `0x1800098c4`
- `0x18001d2a4`
- `0x180020dc0`
- `0x180020de8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009747`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009725`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009725`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009812`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009812`
- `ntdll!RtlCopyUnicodeString` at `0x1800097e1`
- `ntdll!RtlCopyUnicodeString` at `0x1800097e1`
- `ntdll!RtlAcquireResourceShared` at `0x1800096f9`
- `ntdll!RtlAcquireResourceShared` at `0x1800096f9`
- `ntdll!RtlReleaseResource` at `0x18000975b`
- `ntdll!RtlReleaseResource` at `0x18000975b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180009796`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800097a6`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800097a6`

## pseudocode

```c
RPC_STATUS __fastcall XsProcessPnp(PRPC_ASYNC_STATE pAsync, __int64 a2, char a3, const UNICODE_STRING *a4, DWORD *a5)
{
  struct _UNICODE_STRING *v8; // rax
  __int64 *v9; // rdi
  DWORD LastError; // ebx

  RtlAcquireResourceShared(&stru_18005E3D8, 1u);
  if ( dword_18005E43C )
  {
    v8 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, a4->MaximumLength + 18LL);
    v9 = (__int64 *)v8;
    if ( v8 )
    {
      v8->Buffer = &v8[1].Length;
      LastError = 0;
      v8->MaximumLength = a4->MaximumLength + 2;
      RtlCopyUnicodeString(v8, a4);
      *(_WORD *)(v9[1] + 2 * ((unsigned __int64)*(unsigned __int16 *)v9 >> 1)) = 0;
      if ( a3 == 1 )
      {
        BindToTransport(v9[1]);
        BindOptionalNames(v9[1]);
      }
      else
      {
        I_NetServerTransportDel(v9, qword_18005CDB8);
      }
      LocalFree(v9);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
      }
      LastError = GetLastError();
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
    }
    LastError = 5;
  }
  RtlReleaseResource(&stru_18005E3D8);
  *a5 = LastError;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, LastError);
  }
  if ( LastError )
    return RpcAsyncAbortCall(pAsync, LastError);
  else
    return RpcAsyncCompleteCall(pAsync, 0);
}

```

## disassembly

```asm
0x1800096d0  push    rbx
0x1800096d2  push    rsi
0x1800096d3  sub     rsp, 28h
0x1800096d7  mov     [rsp+38h+arg_0], rbp
0x1800096dc  mov     rsi, rcx
0x1800096df  mov     [rsp+38h+arg_10], r14
0x1800096e4  lea     rcx, stru_18005E3D8; Resource
0x1800096eb  mov     dl, 1; Wait
0x1800096ed  mov     [rsp+38h+var_18], r15
0x1800096f2  movzx   r14d, r8b
0x1800096f6  mov     rbp, r9
0x1800096f9  call    cs:__imp_RtlAcquireResourceShared
0x1800096ff  cmp     cs:dword_18005E43C, 0
0x180009706  lea     r15, WPP_GLOBAL_Control
0x18000970d  jz      loc_1800097AE
0x180009713  movzx   edx, word ptr [rbp+2]
0x180009717  mov     ecx, 40h ; '@'; uFlags
0x18000971c  add     rdx, 12h; uBytes
0x180009720  mov     [rsp+38h+arg_8], rdi
0x180009725  call    cs:__imp_LocalAlloc
0x18000972b  mov     rdi, rax
0x18000972e  test    rax, rax
0x180009731  jnz     loc_1800097C5
0x180009737  mov     rcx, cs:WPP_GLOBAL_Control
0x18000973e  cmp     rcx, r15
0x180009741  jnz     loc_18000988D
0x180009747  call    cs:__imp_GetLastError
0x18000974d  mov     ebx, eax
0x18000974f  mov     rdi, [rsp+38h+arg_8]
0x180009754  lea     rcx, stru_18005E3D8; Resource
0x18000975b  call    cs:__imp_RtlReleaseResource
0x180009761  mov     rax, [rsp+38h+arg_20]
0x180009766  mov     [rax], ebx
0x180009768  mov     rcx, cs:WPP_GLOBAL_Control
0x18000976f  mov     r14, [rsp+38h+arg_10]
0x180009774  cmp     rcx, r15
0x180009777  mov     r15, [rsp+38h+var_18]
0x18000977c  mov     rbp, [rsp+38h+arg_0]
0x180009781  jnz     loc_18000981D
0x180009787  mov     rcx, rsi; pAsync
0x18000978a  test    ebx, ebx
0x18000978c  jnz     short loc_1800097A4
0x18000978e  xor     edx, edx
0x180009790  add     rsp, 28h
0x180009794  pop     rsi
0x180009795  pop     rbx
0x180009796  jmp     cs:__imp_RpcAsyncCompleteCall
0x18000979d  add     rsp, 28h
0x1800097a1  pop     rsi
0x1800097a2  pop     rbx
0x1800097a3  retn
0x1800097a4  mov     edx, ebx; ExceptionCode
0x1800097a6  call    cs:__imp_RpcAsyncAbortCall
0x1800097ac  jmp     short loc_18000979D
0x1800097ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097b5  cmp     rcx, r15
0x1800097b8  jnz     loc_18000985F
0x1800097be  mov     ebx, 5
0x1800097c3  jmp     short loc_180009754
0x1800097c5  add     rax, 10h
0x1800097c9  mov     rdx, rbp; SourceString
0x1800097cc  mov     [rdi+8], rax
0x1800097d0  mov     rcx, rdi; DestinationString
0x1800097d3  movzx   eax, word ptr [rbp+2]
0x1800097d7  xor     ebx, ebx
0x1800097d9  add     ax, 2
0x1800097dd  mov     [rdi+2], ax
0x1800097e1  call    cs:__imp_RtlCopyUnicodeString
0x1800097e7  movzx   edx, word ptr [rdi]
0x1800097ea  xor     eax, eax
0x1800097ec  mov     rcx, [rdi+8]
0x1800097f0  shr     rdx, 1
0x1800097f3  mov     [rcx+rdx*2], ax
0x1800097f7  cmp     r14b, 1
0x1800097fb  jnz     short loc_18000984E
0x1800097fd  mov     rcx, [rdi+8]
0x180009801  call    BindToTransport
0x180009806  mov     rcx, [rdi+8]
0x18000980a  call    BindOptionalNames
0x18000980f  mov     rcx, rdi; hMem
0x180009812  call    cs:__imp_LocalFree
0x180009818  jmp     loc_18000974F
0x18000981d  test    byte ptr [rcx+1Ch], 10h
0x180009821  jz      loc_180009787
0x180009827  cmp     byte ptr [rcx+19h], 1
0x18000982b  jb      loc_180009787
0x180009831  mov     rcx, [rcx+10h]
0x180009835  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x18000983c  mov     edx, 28h ; '('
0x180009841  mov     r9d, ebx
0x180009844  call    WPP_SF_d
0x180009849  jmp     loc_180009787
0x18000984e  mov     rdx, cs:qword_18005CDB8
0x180009855  mov     rcx, rdi
0x180009858  call    I_NetServerTransportDel
0x18000985d  jmp     short loc_18000980F
0x18000985f  test    byte ptr [rcx+1Ch], 10h
0x180009863  jz      loc_1800097BE
0x180009869  cmp     byte ptr [rcx+19h], 1
0x18000986d  jb      loc_1800097BE
0x180009873  mov     rcx, [rcx+10h]
0x180009877  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x18000987e  mov     edx, 26h ; '&'
0x180009883  call    WPP_SF_
0x180009888  jmp     loc_1800097BE
0x18000988d  test    byte ptr [rcx+1Ch], 10h
0x180009891  jz      loc_180009747
0x180009897  cmp     byte ptr [rcx+19h], 1
0x18000989b  jb      loc_180009747
0x1800098a1  mov     rcx, [rcx+10h]
0x1800098a5  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800098ac  mov     edx, 27h ; '''
0x1800098b1  call    WPP_SF_
0x1800098b6  jmp     loc_180009747
```
