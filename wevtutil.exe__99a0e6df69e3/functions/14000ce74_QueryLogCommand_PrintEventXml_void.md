# QueryLogCommand::PrintEventXml(void *)

- ea: `0x14000ce74`
- end: `0x14000cfb3`
- name: `?PrintEventXml@QueryLogCommand@@AEAAXPEAX@Z`
- size: `319`
- prototype: `void __fastcall(QueryLogCommand *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c928`

## callees

- `0x14000ce74`
- `0x14000cfbc`
- `0x14000d144`
- `0x140010450`
- `0x140022cec`
- `0x140027780`
- `0x140031810`

## pseudocode

```c
void __fastcall QueryLogCommand::PrintEventXml(QueryLogCommand *this, void *a2)
{
  _QWORD *v2; // rbx
  unsigned int v4; // edi
  _BYTE *v5; // rdx
  _BYTE *v6; // rdx
  __int64 v7; // rax
  void *v8; // rcx
  const char *v9; // [rsp+20h] [rbp-78h]
  _QWORD v10[2]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+50h] [rbp-48h] BYREF
  char v12; // [rsp+A0h] [rbp+8h] BYREF
  DWORD v13; // [rsp+B0h] [rbp+18h] BYREF

  v2 = (_QWORD *)((char *)this + 200);
  v13 = 0;
  v4 = RenderEvent(0, a2, 1u, &v13);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, v4);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v4, 0, 0, v9, 379, 0x1Bu, 0);
    throw (EvtException *)pExceptionObject;
  }
  v5 = (_BYTE *)v2[1];
  v12 = 13;
  if ( v5 == (_BYTE *)v2[2] )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(v2, v5, &v12);
  }
  else
  {
    *v5 = 13;
    ++v2[1];
  }
  v6 = (_BYTE *)v2[1];
  v12 = 10;
  if ( v6 == (_BYTE *)v2[2] )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(v2, v6, &v12);
  }
  else
  {
    *v6 = 10;
    ++v2[1];
  }
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(*v2 + 2 * v7) );
  v10[0] = *v2;
  v8 = (void *)*((_QWORD *)this + 2);
  v10[1] = v7;
  FilePuts(v8, v10);
}

```

## disassembly

```asm
0x14000ce74  mov     rax, rsp
0x14000ce77  mov     [rax+10h], rbx
0x14000ce7b  push    rbp
0x14000ce7c  push    rsi
0x14000ce7d  push    rdi
0x14000ce7e  sub     rsp, 80h
0x14000ce85  lea     rbx, [rcx+0C8h]
0x14000ce8c  xor     ebp, ebp
0x14000ce8e  mov     [rax+18h], ebp
0x14000ce91  lea     rax, [rax+18h]
0x14000ce95  mov     rsi, rcx
0x14000ce98  mov     [rsp+98h+var_78], rax; char *
0x14000ce9d  mov     r9, rbx
0x14000cea0  xor     ecx, ecx; Context
0x14000cea2  lea     r8d, [rbp+1]; Flags
0x14000cea6  call    ?RenderEvent@@YAKPEAX0KAEAV?$vector@EV?$allocator@E@std@@@std@@AEAK@Z; RenderEvent(void *,void *,ulong,std::vector<uchar> &,ulong &)
0x14000ceab  mov     edi, eax
0x14000cead  test    eax, eax
0x14000ceaf  jz      short loc_14000CF22
0x14000ceb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ceb8  lea     rax, WPP_GLOBAL_Control
0x14000cebf  cmp     rcx, rax
0x14000cec2  jz      short loc_14000CEE9
0x14000cec4  test    dword ptr [rcx+1Ch], 400000h
0x14000cecb  jz      short loc_14000CEE9
0x14000cecd  cmp     byte ptr [rcx+19h], 2
0x14000ced1  jb      short loc_14000CEE9
0x14000ced3  mov     rcx, [rcx+10h]
0x14000ced7  lea     edx, [rbp+1Ah]
0x14000ceda  mov     r9d, edi
0x14000cedd  lea     r8, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids
0x14000cee4  call    WPP_SF_d
0x14000cee9  mov     [rsp+98h+Src], rbp; Src
0x14000ceee  lea     rcx, [rsp+98h+pExceptionObject]; this
0x14000cef3  mov     [rsp+98h+var_68], 1Bh; unsigned int
0x14000cefb  xor     r9d, r9d; unsigned int
0x14000cefe  xor     r8d, r8d; unsigned int
0x14000cf01  mov     [rsp+98h+var_70], 17Bh; int
0x14000cf09  mov     edx, edi; unsigned int
0x14000cf0b  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000cf10  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000cf17  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x14000cf1c  call    _CxxThrowException_0
0x14000cf22  mov     rdx, [rbx+8]
0x14000cf26  mov     [rsp+98h+arg_0], 0Dh
0x14000cf2e  cmp     rdx, [rbx+10h]
0x14000cf32  jz      short loc_14000CF3D
0x14000cf34  mov     byte ptr [rdx], 0Dh
0x14000cf37  inc     qword ptr [rbx+8]
0x14000cf3b  jmp     short loc_14000CF4D
0x14000cf3d  lea     r8, [rsp+98h+arg_0]
0x14000cf45  mov     rcx, rbx
0x14000cf48  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x14000cf4d  mov     rdx, [rbx+8]
0x14000cf51  mov     [rsp+98h+arg_0], 0Ah
0x14000cf59  cmp     rdx, [rbx+10h]
0x14000cf5d  jz      short loc_14000CF68
0x14000cf5f  mov     byte ptr [rdx], 0Ah
0x14000cf62  inc     qword ptr [rbx+8]
0x14000cf66  jmp     short loc_14000CF78
0x14000cf68  lea     r8, [rsp+98h+arg_0]
0x14000cf70  mov     rcx, rbx
0x14000cf73  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x14000cf78  mov     rcx, [rbx]
0x14000cf7b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000cf7f  inc     rax
0x14000cf82  cmp     [rcx+rax*2], bp
0x14000cf86  jnz     short loc_14000CF7F
0x14000cf88  mov     [rsp+98h+var_58], rcx
0x14000cf8d  lea     rdx, [rsp+98h+var_58]
0x14000cf92  mov     rcx, [rsi+10h]; hFile
0x14000cf96  mov     [rsp+98h+var_50], rax
0x14000cf9b  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14000cfa0  mov     rbx, [rsp+98h+arg_8]
0x14000cfa8  add     rsp, 80h
0x14000cfaf  pop     rdi
0x14000cfb0  pop     rsi
0x14000cfb1  pop     rbp
0x14000cfb2  retn
```
