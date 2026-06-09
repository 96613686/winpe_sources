# I_DecodeLongReturn(uchar *,ulong)

- ea: `0x180012878`
- end: `0x180012982`
- name: `?I_DecodeLongReturn@@YAJPEAEK@Z`
- size: `266`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180011318`
- `0x180012a78`
- `0x180012c10`
- `0x180016d20`
- `0x18002b490`
- `0x18002b734`
- `0x18002c15c`
- `0x18002db5c`
- `0x18002e010`

## callees

- `0x180007bc0`
- `0x180012878`
- `0x18001991c`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x1800128dc`
- `RPCRT4!NdrMesTypeDecode3` at `0x1800128dc`
- `RPCRT4!NdrMesTypeFree3` at `0x180012917`
- `RPCRT4!NdrMesTypeFree3` at `0x180012917`
- `RPCRT4!MesHandleFree` at `0x180012974`
- `RPCRT4!MesHandleFree` at `0x180012974`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180012894`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180012894`

## pseudocode

```c
__int64 __fastcall I_DecodeLongReturn(char *a1, unsigned int a2)
{
  unsigned int v2; // ebx
  handle_t pHandle; // [rsp+30h] [rbp-18h] BYREF
  unsigned int pObject; // [rsp+60h] [rbp+18h] BYREF
  unsigned int v6; // [rsp+68h] [rbp+20h]

  pHandle = 0;
  pObject = 0;
  if ( MesDecodeBufferHandleCreate(a1, a2, &pHandle) )
  {
    v2 = -2146435041;
  }
  else
  {
    pObject = 0;
    NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, &pObject);
    v2 = pObject;
    v6 = pObject;
    NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, &pObject);
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  return v2;
}

```

## disassembly

```asm
0x180012878  push    rbx
0x18001287a  sub     rsp, 40h
0x18001287e  mov     [rsp+48h+pHandle], 0
0x180012887  mov     [rsp+48h+arg_10], 0
0x18001288f  lea     r8, [rsp+48h+pHandle]; pHandle
0x180012894  call    cs:__imp_MesDecodeBufferHandleCreate
0x18001289a  test    eax, eax
0x18001289c  jz      short loc_1800128A8
0x18001289e  mov     ebx, 8010001Fh
0x1800128a3  jmp     loc_18001296A
0x1800128a8  mov     [rsp+48h+arg_10], 0
0x1800128b0  lea     rax, [rsp+48h+arg_10]
0x1800128b5  mov     [rsp+48h+pObject], rax; pObject
0x1800128ba  mov     [rsp+48h+nTypeIndex], 0; nTypeIndex
0x1800128c2  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800128c9  lea     r8, pProxyInfo; pProxyInfo
0x1800128d0  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800128d7  mov     rcx, [rsp+48h+pHandle]; Handle
0x1800128dc  call    cs:__imp_NdrMesTypeDecode3
0x1800128e2  nop
0x1800128e3  mov     ebx, [rsp+48h+arg_10]
0x1800128e7  mov     [rsp+48h+arg_18], ebx
0x1800128eb  lea     rax, [rsp+48h+arg_10]
0x1800128f0  mov     [rsp+48h+pObject], rax; pObject
0x1800128f5  mov     [rsp+48h+nTypeIndex], 0; nTypeIndex
0x1800128fd  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180012904  lea     r8, pProxyInfo; pProxyInfo
0x18001290b  lea     rdx, pPicklingInfo; pPicklingInfo
0x180012912  mov     rcx, [rsp+48h+pHandle]; Handle
0x180012917  call    cs:__imp_NdrMesTypeFree3
0x18001291d  jmp     short loc_18001296A
0x18001291f  mov     ebx, [rsp+48h+arg_18]
0x180012923  jmp     short loc_18001296A
0x180012925  mov     ebx, eax
0x180012927  mov     edx, 2
0x18001292c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012931  lea     rax, WPP_GLOBAL_Control
0x180012938  mov     rcx, cs:WPP_GLOBAL_Control
0x18001293f  cmp     rcx, rax
0x180012942  jz      short loc_18001296A
0x180012944  test    byte ptr [rcx+1Ch], 8
0x180012948  jz      short loc_18001296A
0x18001294a  cmp     byte ptr [rcx+19h], 2
0x18001294e  jb      short loc_18001296A
0x180012950  mov     edx, 20h ; ' '
0x180012955  mov     [rsp+48h+nTypeIndex], ebx
0x180012959  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180012960  mov     rcx, [rcx+10h]
0x180012964  call    WPP_SF_sd
0x180012969  nop
0x18001296a  mov     rcx, [rsp+48h+pHandle]; Handle
0x18001296f  test    rcx, rcx
0x180012972  jz      short loc_18001297A
0x180012974  call    cs:__imp_MesHandleFree
0x18001297a  mov     eax, ebx
0x18001297c  add     rsp, 40h
0x180012980  pop     rbx
0x180012981  retn
```
