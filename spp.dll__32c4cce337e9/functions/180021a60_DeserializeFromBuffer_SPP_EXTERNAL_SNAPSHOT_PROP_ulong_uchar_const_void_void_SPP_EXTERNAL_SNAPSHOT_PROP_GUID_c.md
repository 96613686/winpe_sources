# DeserializeFromBuffer<_SPP_EXTERNAL_SNAPSHOT_PROP>(ulong,uchar const *,void (*)(void *,_SPP_EXTERNAL_SNAPSHOT_PROP *),_GUID const *,_SPP_EXTERNAL_SNAPSHOT_PROP *)

- ea: `0x180021a60`
- end: `0x180021ca9`
- name: `??$DeserializeFromBuffer@U_SPP_EXTERNAL_SNAPSHOT_PROP@@@@YAJKPEBEP6AXPEAXPEAU_SPP_EXTERNAL_SNAPSHOT_PROP@@@ZPEBU_GUID@@2@Z`
- size: `585`
- prototype: `__int64(size_t Size, UCHAR *Src, __int64, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009bb0`

## callees

- `0x180020710`
- `0x180021a60`
- `0x180022500`
- `0x1800268b4`
- `0x1800269ac`
- `0x180035b82`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x180021be4`
- `ntdll!RtlComputeCrc32` at `0x180021be4`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180021c0d`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180021c0d`
- `RPCRT4!MesHandleFree` at `0x180021c6f`
- `RPCRT4!MesHandleFree` at `0x180021c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021b5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021b5e`

## string_xrefs

- `0x180021ab6`: `DeserializeFromBuffer`

## pseudocode

```c
__int64 DeserializeFromBuffer<_SPP_EXTERNAL_SNAPSHOT_PROP>(size_t Size, UCHAR *Src, __int64 a3, ...)
{
  size_t v4; // rsi
  void *v5; // r15
  _BYTE *v6; // rax
  __int64 v7; // rcx
  __int16 v8; // ax
  LPVOID v9; // rax
  void *v10; // rbx
  __int64 v11; // rax
  bool v12; // zf
  ULONG v13; // esi
  int v14; // eax
  bool v15; // sf
  signed int v16; // eax
  unsigned int v17; // ebx
  int v19; // [rsp+20h] [rbp-40h] BYREF
  __int16 v20; // [rsp+24h] [rbp-3Ch]
  __int16 v21; // [rsp+26h] [rbp-3Ah]
  handle_t pHandle; // [rsp+98h] [rbp+38h] BYREF
  va_list pHandlea; // [rsp+98h] [rbp+38h]
  __int64 v24; // [rsp+A0h] [rbp+40h]
  va_list va1; // [rsp+A8h] [rbp+48h] BYREF

  va_start(va1, a3);
  va_start(pHandlea, a3);
  pHandle = va_arg(va1, handle_t);
  v24 = va_arg(va1, _QWORD);
  v4 = (unsigned int)Size;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v19, "DeserializeFromBuffer", 0x13Cu, 1u);
  v5 = 0;
  pHandle = 0;
  if ( v24 )
  {
    v6 = (_BYTE *)v24;
    v7 = 184;
    do
    {
      *v6++ = 0;
      --v7;
    }
    while ( v7 );
  }
  v8 = 327;
  if ( !(_DWORD)v4 )
    goto LABEL_8;
  v20 = 327;
  if ( !Src )
  {
    v8 = 328;
LABEL_8:
    v19 = -2147024809;
LABEL_9:
    v21 = v8;
    goto LABEL_30;
  }
  v20 = 330;
  v8 = 331;
  if ( !v24 )
    goto LABEL_8;
  v20 = 331;
  v8 = 336;
  if ( (unsigned int)v4 <= 0x18 )
  {
LABEL_14:
    v19 = -2147024883;
    goto LABEL_9;
  }
  v20 = 336;
  v19 = 0;
  if ( Src != (UCHAR *)((unsigned __int64)(Src + 7) & 0xFFFFFFFFFFFFFFF8uLL) )
  {
    v9 = CoTaskMemAlloc((unsigned int)(v4 + 7));
    v5 = v9;
    if ( !v9 )
    {
      v19 = -2147024882;
      v21 = 346;
      goto LABEL_30;
    }
    v20 = 346;
    v10 = (void *)(((unsigned __int64)v9 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
    v19 = 0;
    memcpy_0(v10, Src, v4);
    Src = (UCHAR *)v10;
  }
  v11 = *(_QWORD *)Src - 0x43B5FB0304C846DDLL;
  if ( *(_QWORD *)Src == 0x43B5FB0304C846DDLL )
    v11 = *((_QWORD *)Src + 1) - 0x780ECED7F2672ABBLL;
  v12 = v11 == 0;
  v8 = 356;
  if ( !v12 )
    goto LABEL_14;
  v13 = v4 - 24;
  v19 = 0;
  v20 = 356;
  v12 = *((_DWORD *)Src + 4) == RtlComputeCrc32(0x5EED5FA5u, Src + 24, v13);
  v8 = 358;
  if ( !v12 )
    goto LABEL_14;
  v19 = 0;
  v20 = 358;
  v14 = MesDecodeBufferHandleCreate((char *)Src + 24, v13, (handle_t *)pHandlea);
  if ( v14 > 0 )
    v14 = (unsigned __int16)v14 | 0x80070000;
  v19 = v14;
  v15 = v14 < 0;
  v8 = 363;
  if ( v15 )
    goto LABEL_9;
  v20 = 363;
  v16 = InvokeCoder<_SPP_METADATA_PROP>(pHandle, SPP_EXTERNAL_SNAPSHOT_PROP_Decode, v24);
  if ( v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x80070000;
  v19 = v16;
  v15 = v16 < 0;
  v8 = 365;
  if ( v15 )
    goto LABEL_9;
  v20 = 365;
LABEL_30:
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  CoTaskMemFree(v5);
  v17 = v19;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v19);
  return v17;
}

```

## disassembly

```asm
0x180021a60  mov     [rsp-18h+arg_0], rbx
0x180021a65  mov     [rsp-18h+arg_8], rsi
0x180021a6a  mov     [rsp-18h+pHandle], r9
0x180021a6f  push    rbp
0x180021a70  push    rdi
0x180021a71  push    r15
0x180021a73  mov     rbp, rsp
0x180021a76  sub     rsp, 60h
0x180021a7a  mov     rdi, rdx
0x180021a7d  mov     esi, ecx
0x180021a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a86  lea     rax, WPP_GLOBAL_Control
0x180021a8d  cmp     rcx, rax
0x180021a90  jz      short loc_180021AB0
0x180021a92  test    dword ptr [rcx+1Ch], 20000000h
0x180021a99  jz      short loc_180021AB0
0x180021a9b  mov     rcx, [rcx+10h]
0x180021a9f  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x180021aa6  mov     edx, 13h
0x180021aab  call    WPP_SF_
0x180021ab0  mov     r9d, 1; unsigned __int16
0x180021ab6  lea     rdx, aDeserializefro_0; "DeserializeFromBuffer"
0x180021abd  mov     r8d, 13Ch; unsigned __int16
0x180021ac3  lea     rcx, [rbp+var_40]; this
0x180021ac7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180021acc  xor     r15d, r15d
0x180021acf  mov     [rbp+pHandle], 0
0x180021ad7  cmp     [rbp+arg_20], r15
0x180021adb  jz      short loc_180021AF2
0x180021add  mov     rax, [rbp+arg_20]
0x180021ae1  mov     ecx, 0B8h
0x180021ae6  mov     [rax], r15b
0x180021ae9  inc     rax
0x180021aec  sub     rcx, 1
0x180021af0  jnz     short loc_180021AE6
0x180021af2  mov     eax, 147h
0x180021af7  test    esi, esi
0x180021af9  jnz     short loc_180021B0B
0x180021afb  mov     [rbp+var_40], 80070057h
0x180021b02  mov     [rbp+var_3A], ax
0x180021b06  jmp     loc_180021C66
0x180021b0b  mov     [rbp+var_3C], ax
0x180021b0f  test    rdi, rdi
0x180021b12  jnz     short loc_180021B1B
0x180021b14  mov     eax, 148h
0x180021b19  jmp     short loc_180021AFB
0x180021b1b  mov     eax, 14Ah
0x180021b20  mov     [rbp+var_3C], ax
0x180021b24  mov     eax, 14Bh
0x180021b29  cmp     [rbp+arg_20], r15
0x180021b2d  jz      short loc_180021AFB
0x180021b2f  mov     [rbp+var_3C], ax
0x180021b33  mov     eax, 150h
0x180021b38  cmp     esi, 18h
0x180021b3b  ja      short loc_180021B46
0x180021b3d  mov     [rbp+var_40], 8007000Dh
0x180021b44  jmp     short loc_180021B02
0x180021b46  mov     [rbp+var_3C], ax
0x180021b4a  lea     rax, [rdi+7]
0x180021b4e  and     rax, 0FFFFFFFFFFFFFFF8h
0x180021b52  mov     [rbp+var_40], r15d
0x180021b56  cmp     rdi, rax
0x180021b59  jz      short loc_180021BA5
0x180021b5b  lea     ecx, [rsi+7]; cb
0x180021b5e  call    cs:__imp_CoTaskMemAlloc
0x180021b64  mov     r15, rax
0x180021b67  mov     ecx, 15Ah
0x180021b6c  test    rax, rax
0x180021b6f  jnz     short loc_180021B81
0x180021b71  mov     [rbp+var_40], 8007000Eh
0x180021b78  mov     [rbp+var_3A], cx
0x180021b7c  jmp     loc_180021C66
0x180021b81  lea     rbx, [rax+7]
0x180021b85  mov     [rbp+var_3C], cx
0x180021b89  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180021b8d  mov     [rbp+var_40], 0
0x180021b94  mov     rcx, rbx; void *
0x180021b97  mov     r8, rsi; Size
0x180021b9a  mov     rdx, rdi; Src
0x180021b9d  call    memcpy_0
0x180021ba2  mov     rdi, rbx
0x180021ba5  mov     rax, [rdi]
0x180021ba8  sub     rax, qword ptr cs:xmmword_18003C2D0
0x180021baf  jnz     short loc_180021BBC
0x180021bb1  mov     rax, [rdi+8]
0x180021bb5  sub     rax, qword ptr cs:xmmword_18003C2D0+8
0x180021bbc  test    rax, rax
0x180021bbf  mov     eax, 164h
0x180021bc4  jnz     loc_180021B3D
0x180021bca  add     esi, 0FFFFFFE8h
0x180021bcd  mov     [rbp+var_40], 0
0x180021bd4  mov     r8d, esi; Length
0x180021bd7  mov     [rbp+var_3C], ax
0x180021bdb  lea     rdx, [rdi+18h]; Buffer
0x180021bdf  mov     ecx, 5EED5FA5h; InitialCrc
0x180021be4  call    cs:__imp_RtlComputeCrc32
0x180021bea  cmp     [rdi+10h], eax
0x180021bed  mov     eax, 166h
0x180021bf2  jnz     loc_180021B3D
0x180021bf8  lea     r8, [rbp+pHandle]; pHandle
0x180021bfc  mov     [rbp+var_40], 0
0x180021c03  mov     edx, esi; BufferSize
0x180021c05  mov     [rbp+var_3C], ax
0x180021c09  lea     rcx, [rdi+18h]; Buffer
0x180021c0d  call    cs:__imp_MesDecodeBufferHandleCreate
0x180021c13  mov     ebx, 80070000h
0x180021c18  test    eax, eax
0x180021c1a  jle     short loc_180021C21
0x180021c1c  movzx   eax, ax
0x180021c1f  or      eax, ebx
0x180021c21  mov     [rbp+var_40], eax
0x180021c24  test    eax, eax
0x180021c26  mov     eax, 16Bh
0x180021c2b  js      loc_180021B02
0x180021c31  mov     r8, [rbp+arg_20]
0x180021c35  lea     rdx, SPP_EXTERNAL_SNAPSHOT_PROP_Decode
0x180021c3c  mov     rcx, [rbp+pHandle]
0x180021c40  mov     [rbp+var_3C], ax
0x180021c44  call    ??$InvokeCoder@U_SPP_METADATA_PROP@@@@YAJPEAXP6AX0PEAU_SPP_METADATA_PROP@@@Z1@Z; InvokeCoder<_SPP_METADATA_PROP>(void *,void (*)(void *,_SPP_METADATA_PROP *),_SPP_METADATA_PROP *)
0x180021c49  test    eax, eax
0x180021c4b  jle     short loc_180021C52
0x180021c4d  movzx   eax, ax
0x180021c50  or      eax, ebx
0x180021c52  mov     [rbp+var_40], eax
0x180021c55  test    eax, eax
0x180021c57  mov     eax, 16Dh
0x180021c5c  js      loc_180021B02
0x180021c62  mov     [rbp+var_3C], ax
0x180021c66  mov     rcx, [rbp+pHandle]; Handle
0x180021c6a  test    rcx, rcx
0x180021c6d  jz      short loc_180021C7D
0x180021c6f  call    cs:__imp_MesHandleFree
0x180021c75  mov     [rbp+pHandle], 0
0x180021c7d  mov     rcx, r15; pv
0x180021c80  call    cs:__imp_CoTaskMemFree
0x180021c86  mov     ebx, [rbp+var_40]
0x180021c89  lea     rcx, [rbp+var_40]; this
0x180021c8d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180021c92  lea     r11, [rsp+60h+var_s0]
0x180021c97  mov     eax, ebx
0x180021c99  mov     rbx, [r11+20h]
0x180021c9d  mov     rsi, [r11+28h]
0x180021ca1  mov     rsp, r11
0x180021ca4  pop     r15
0x180021ca6  pop     rdi
0x180021ca7  pop     rbp
0x180021ca8  retn
```
