# WriteBlankChunk(void *,unsigned __int64,unsigned __int64,bool)

- ea: `0x180033f34`
- end: `0x180034096`
- name: `?WriteBlankChunk@@YAXPEAX_K1_N@Z`
- size: `354`
- prototype: `void __fastcall(void *, unsigned __int64, unsigned __int64, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800314f0`
- `0x18003459c`

## callees

- `0x180023548`
- `0x180023a28`
- `0x180024a50`
- `0x180025514`
- `0x180033b4c`
- `0x180033c4c`
- `0x180033f34`
- `0x180034fd8`
- `0x180034ffc`
- `0x180035338`
- `0x180038fa4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WriteBlankChunk(void *a1, unsigned __int64 a2, __int64 a3, char a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  ULONG v10; // eax
  unsigned int v11; // ebx
  _BYTE pExceptionObject[48]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v13[8]; // [rsp+50h] [rbp-B0h] BYREF
  PUCHAR Buffer[4]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v15; // [rsp+78h] [rbp-88h]
  void *v16; // [rsp+98h] [rbp-68h]
  void *v17; // [rsp+1B0h] [rbp+B0h]

  WriteFileView::WriteFileView((WriteFileView *)v13, a2, 1);
  Buffer[1] = (PUCHAR)((a3 << 16) + 4096);
  InitializeChunkHeaderInfo((struct ChunkHeader *)Buffer[0], a2);
  memset_0(v16, 0, 0x100u);
  memset_0(v17, 0, 0x80u);
  if ( a4 )
  {
    *((_DWORD *)Buffer[0] + 31) = 0;
    *((_DWORD *)Buffer[0] + 30) |= 4u;
  }
  else
  {
    v10 = CalcGeneralHeaderCRC(Buffer[0], v8, v9, 512);
    *((_DWORD *)Buffer[0] + 31) = v10;
  }
  v11 = FileView::ActualWrite((FileView *)Buffer, a1, 0, v15);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d678aa4655f1354a2fe0a66ad85eee91_Traceguids, v11);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v11);
    throw (EvtException *)pExceptionObject;
  }
  FileView::~FileView((FileView *)Buffer);
}

```

## disassembly

```asm
0x180033f34  mov     [rsp-8+arg_8], rbx
0x180033f39  mov     [rsp-8+arg_10], rsi
0x180033f3e  push    rbp
0x180033f3f  push    rdi
0x180033f40  push    r14
0x180033f42  lea     rbp, [rsp-150h]
0x180033f4a  sub     rsp, 250h
0x180033f51  mov     rax, cs:__security_cookie
0x180033f58  xor     rax, rsp
0x180033f5b  mov     [rbp+160h+var_20], rax
0x180033f62  mov     sil, r9b
0x180033f65  mov     rbx, r8
0x180033f68  mov     rdi, rdx
0x180033f6b  mov     r14, rcx
0x180033f6e  mov     r8b, 1; bool
0x180033f71  lea     rcx, [rsp+260h+var_210]; this
0x180033f76  call    ??0WriteFileView@@QEAA@K_N@Z; WriteFileView::WriteFileView(ulong,bool)
0x180033f7b  nop
0x180033f7c  shl     rbx, 10h
0x180033f80  add     rbx, 1000h
0x180033f87  mov     [rsp+260h+var_200], rbx
0x180033f8c  mov     rdx, rdi; unsigned __int64
0x180033f8f  mov     rcx, [rsp+260h+Buffer]; struct ChunkHeader *
0x180033f94  call    ?InitializeChunkHeaderInfo@@YAXPEAUChunkHeader@@_K@Z; InitializeChunkHeaderInfo(ChunkHeader *,unsigned __int64)
0x180033f99  xor     edx, edx; Val
0x180033f9b  mov     r8d, 100h; Size
0x180033fa1  mov     rcx, [rbp+160h+var_1C8]; void *
0x180033fa5  call    memset_0
0x180033faa  xor     edx, edx; Val
0x180033fac  mov     r8d, 80h; Size
0x180033fb2  mov     rcx, [rbp+160h+var_B0]; void *
0x180033fb9  call    memset_0
0x180033fbe  test    sil, sil
0x180033fc1  jz      short loc_180033FDA
0x180033fc3  mov     rax, [rsp+260h+Buffer]
0x180033fc8  mov     dword ptr [rax+7Ch], 0
0x180033fcf  mov     rax, [rsp+260h+Buffer]
0x180033fd4  or      dword ptr [rax+78h], 4
0x180033fd8  jmp     short loc_180033FF2
0x180033fda  mov     r9d, 200h; unsigned int
0x180033fe0  mov     rcx, [rsp+260h+Buffer]; Buffer
0x180033fe5  call    ?CalcGeneralHeaderCRC@@YAKPEBEKKK@Z; CalcGeneralHeaderCRC(uchar const *,ulong,ulong,ulong)
0x180033fea  mov     rcx, [rsp+260h+Buffer]
0x180033fef  mov     [rcx+7Ch], eax
0x180033ff2  mov     r9d, [rsp+260h+var_1E8]; unsigned int
0x180033ff7  xor     r8d, r8d; unsigned int
0x180033ffa  mov     rdx, r14; void *
0x180033ffd  lea     rcx, [rsp+260h+Buffer]; this
0x180034002  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180034007  mov     ebx, eax
0x180034009  test    eax, eax
0x18003400b  jnz     short loc_18003403E
0x18003400d  lea     rcx, [rsp+260h+Buffer]; this
0x180034012  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x180034017  mov     rcx, [rbp+160h+var_20]
0x18003401e  xor     rcx, rsp; StackCookie
0x180034021  call    __security_check_cookie
0x180034026  lea     r11, [rsp+260h+var_10]
0x18003402e  mov     rbx, [r11+28h]
0x180034032  mov     rsi, [r11+30h]
0x180034036  mov     rsp, r11
0x180034039  pop     r14
0x18003403b  pop     rdi
0x18003403c  pop     rbp
0x18003403d  retn
0x18003403e  lea     rax, WPP_GLOBAL_Control
0x180034045  mov     rcx, cs:WPP_GLOBAL_Control
0x18003404c  cmp     rcx, rax
0x18003404f  jz      short loc_180034078
0x180034051  test    dword ptr [rcx+1Ch], 8000h
0x180034058  jz      short loc_180034078
0x18003405a  cmp     byte ptr [rcx+19h], 2
0x18003405e  jb      short loc_180034078
0x180034060  mov     edx, 0Ah
0x180034065  mov     r9d, ebx
0x180034068  lea     r8, WPP_d678aa4655f1354a2fe0a66ad85eee91_Traceguids
0x18003406f  mov     rcx, [rcx+10h]
0x180034073  call    WPP_SF_D
0x180034078  mov     edx, ebx; unsigned int
0x18003407a  lea     rcx, [rsp+260h+pExceptionObject]; this
0x18003407f  call    ??0EvtException@@QEAA@K@Z; EvtException::EvtException(ulong)
0x180034084  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003408b  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x180034090  call    _CxxThrowException_0
```
