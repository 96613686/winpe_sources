# __C_specific_handler

- ea: `0x140002d48`
- end: `0x140002f5f`
- name: `__C_specific_handler`
- size: `535`
- prototype: `EXCEPTION_DISPOSITION __cdecl(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400058b0`

## callees

- `0x140002bc0`
- `0x140002d48`
- `0x140005240`
- `0x140005270`
- `0x140005278`
- `0x140005820`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlUnwindEx` at `0x140002e64`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlUnwindEx` at `0x140002e64`

## pseudocode

```c
EXCEPTION_DISPOSITION __cdecl _C_specific_handler(
        struct _EXCEPTION_RECORD *ExceptionRecord,
        void *EstablisherFrame,
        struct _CONTEXT *ContextRecord,
        struct _DISPATCHER_CONTEXT *DispatcherContext)
{
  DWORD64 ImageBase; // r12
  DWORD *HandlerData; // rbx
  unsigned __int64 v10; // r14
  DWORD ScopeIndex; // edi
  int v12; // eax
  unsigned __int64 v14; // rbp
  DWORD i; // edx
  __int64 v16; // rcx
  DWORD v17; // r8d
  _QWORD v18[2]; // [rsp+30h] [rbp-38h] BYREF

  _except_validate_context_record(ContextRecord);
  ImageBase = DispatcherContext->ImageBase;
  HandlerData = (DWORD *)DispatcherContext->HandlerData;
  v10 = DispatcherContext->ControlPc - ImageBase;
  ScopeIndex = DispatcherContext->ScopeIndex;
  if ( (ExceptionRecord->ExceptionFlags & 0x66) != 0 )
  {
    v14 = DispatcherContext->TargetIp - ImageBase;
    while ( 1 )
    {
      v17 = *HandlerData;
      if ( ScopeIndex >= *HandlerData )
        break;
      if ( v10 >= HandlerData[4 * ScopeIndex + 1] && v10 < HandlerData[4 * ScopeIndex + 2] )
      {
        if ( (ExceptionRecord->ExceptionFlags & 0x20) != 0 )
        {
          for ( i = 0; i < v17; ++i )
          {
            if ( v14 >= HandlerData[4 * i + 1]
              && v14 < HandlerData[4 * i + 2]
              && HandlerData[4 * i + 4] == HandlerData[4 * ScopeIndex + 4]
              && HandlerData[4 * i + 3] == HandlerData[4 * ScopeIndex + 3] )
            {
              break;
            }
          }
          if ( i != *HandlerData )
            return 1;
        }
        v16 = 2LL * ScopeIndex;
        if ( HandlerData[4 * ScopeIndex + 4] )
        {
          if ( v14 == HandlerData[4 * ScopeIndex + 4] && (ExceptionRecord->ExceptionFlags & 0x20) != 0 )
            return 1;
        }
        else
        {
          DispatcherContext->ScopeIndex = ScopeIndex + 1;
          LOBYTE(v16) = 1;
          ((void (__fastcall *)(__int64, void *))(ImageBase + HandlerData[4 * ScopeIndex + 3]))(v16, EstablisherFrame);
        }
      }
      ++ScopeIndex;
    }
  }
  else
  {
    v18[0] = ExceptionRecord;
    v18[1] = ContextRecord;
    while ( ScopeIndex < *HandlerData )
    {
      if ( v10 >= HandlerData[4 * ScopeIndex + 1]
        && v10 < HandlerData[4 * ScopeIndex + 2]
        && HandlerData[4 * ScopeIndex + 4] )
      {
        if ( HandlerData[4 * ScopeIndex + 3] == 1 )
          goto LABEL_10;
        v12 = ((__int64 (__fastcall *)(_QWORD *, void *))(ImageBase + HandlerData[4 * ScopeIndex + 3]))(
                v18,
                EstablisherFrame);
        if ( v12 < 0 )
          return 0;
        if ( v12 > 0 )
        {
LABEL_10:
          if ( ExceptionRecord->ExceptionCode == -529697949 && pDestructExceptionObject )
          {
            if ( (unsigned int)IsNonwritableInCurrentImage(&pDestructExceptionObject) )
              pDestructExceptionObject(ExceptionRecord, 1);
          }
          NLG_Notify(ImageBase + HandlerData[4 * ScopeIndex + 4], EstablisherFrame, 1);
          RtlUnwindEx(
            EstablisherFrame,
            (PVOID)(ImageBase + HandlerData[4 * ScopeIndex + 4]),
            ExceptionRecord,
            (PVOID)ExceptionRecord->ExceptionCode,
            DispatcherContext->ContextRecord,
            DispatcherContext->HistoryTable);
          _NLG_Return2();
        }
      }
      ++ScopeIndex;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140002d48  mov     [rsp+arg_0], rbx
0x140002d4d  mov     [rsp+arg_8], rbp
0x140002d52  mov     [rsp+arg_10], rsi
0x140002d57  push    rdi
0x140002d58  push    r12
0x140002d5a  push    r13
0x140002d5c  push    r14
0x140002d5e  push    r15
0x140002d60  sub     rsp, 40h
0x140002d64  mov     rsi, rcx
0x140002d67  mov     r15, r9
0x140002d6a  mov     rcx, r8
0x140002d6d  mov     rbp, r8
0x140002d70  mov     r13, rdx
0x140002d73  call    __except_validate_context_record
0x140002d78  mov     r12, [r15+8]
0x140002d7c  mov     r14, [r15]
0x140002d7f  mov     rbx, [r15+38h]
0x140002d83  sub     r14, r12
0x140002d86  test    byte ptr [rsi+4], 66h
0x140002d8a  mov     edi, [r15+48h]
0x140002d8e  jnz     loc_140002E85
0x140002d94  mov     [rsp+68h+var_38], rsi
0x140002d99  mov     [rsp+68h+var_30], rbp
0x140002d9e  jmp     loc_140002E71
0x140002da3  mov     ecx, edi
0x140002da5  add     rcx, rcx
0x140002da8  mov     ebp, edi
0x140002daa  mov     eax, [rbx+rcx*8+4]
0x140002dae  cmp     r14, rax
0x140002db1  jb      loc_140002E6F
0x140002db7  mov     eax, [rbx+rcx*8+8]
0x140002dbb  cmp     r14, rax
0x140002dbe  jnb     loc_140002E6F
0x140002dc4  cmp     dword ptr [rbx+rcx*8+10h], 0
0x140002dc9  jz      loc_140002E6F
0x140002dcf  cmp     dword ptr [rbx+rcx*8+0Ch], 1
0x140002dd4  jz      short loc_140002DF1
0x140002dd6  mov     eax, [rbx+rcx*8+0Ch]
0x140002dda  mov     rdx, r13
0x140002ddd  add     rax, r12
0x140002de0  lea     rcx, [rsp+68h+var_38]
0x140002de5  call    rax
0x140002de7  test    eax, eax
0x140002de9  js      loc_140002E7E
0x140002def  jle     short loc_140002E6F
0x140002df1  cmp     dword ptr [rsi], 0E06D7363h
0x140002df7  jnz     short loc_140002E21
0x140002df9  cmp     cs:_pDestructExceptionObject, 0
0x140002e01  jz      short loc_140002E21
0x140002e03  lea     rcx, _pDestructExceptionObject
0x140002e0a  call    _IsNonwritableInCurrentImage
0x140002e0f  test    eax, eax
0x140002e11  jz      short loc_140002E21
0x140002e13  mov     edx, 1
0x140002e18  mov     rcx, rsi
0x140002e1b  call    cs:_pDestructExceptionObject
0x140002e21  lea     rax, [rbp+1]
0x140002e25  mov     r8d, 1
0x140002e2b  add     rax, rax
0x140002e2e  mov     rdx, r13
0x140002e31  mov     ecx, [rbx+rax*8]
0x140002e34  add     rcx, r12
0x140002e37  call    _NLG_Notify
0x140002e3c  mov     r9d, [rsi]; ReturnValue
0x140002e3f  lea     rax, [rbp+1]
0x140002e43  add     rax, rax
0x140002e46  mov     r8, rsi; ExceptionRecord
0x140002e49  mov     rcx, r13; TargetFrame
0x140002e4c  mov     edx, [rbx+rax*8]
0x140002e4f  mov     rax, [r15+40h]
0x140002e53  add     rdx, r12; TargetIp
0x140002e56  mov     [rsp+68h+HistoryTable], rax; HistoryTable
0x140002e5b  mov     rax, [r15+28h]
0x140002e5f  mov     [rsp+68h+ContextRecord], rax; ContextRecord
0x140002e64  call    cs:__imp_RtlUnwindEx
0x140002e6a  call    __NLG_Return2
0x140002e6f  inc     edi
0x140002e71  cmp     edi, [rbx]
0x140002e73  jb      loc_140002DA3
0x140002e79  jmp     loc_140002F3C
0x140002e7e  xor     eax, eax
0x140002e80  jmp     loc_140002F41
0x140002e85  mov     rbp, [r15+20h]
0x140002e89  sub     rbp, r12
0x140002e8c  jmp     loc_140002F30
0x140002e91  mov     r9d, edi
0x140002e94  add     r9, r9
0x140002e97  mov     eax, [rbx+r9*8+4]
0x140002e9c  cmp     r14, rax
0x140002e9f  jb      loc_140002F2E
0x140002ea5  mov     eax, [rbx+r9*8+8]
0x140002eaa  cmp     r14, rax
0x140002ead  jnb     short loc_140002F2E
0x140002eaf  test    byte ptr [rsi+4], 20h
0x140002eb3  jz      short loc_140002EF4
0x140002eb5  xor     edx, edx
0x140002eb7  test    r8d, r8d
0x140002eba  jz      short loc_140002EF0
0x140002ebc  mov     ecx, edx
0x140002ebe  add     rcx, rcx
0x140002ec1  mov     eax, [rbx+rcx*8+4]
0x140002ec5  cmp     rbp, rax
0x140002ec8  jb      short loc_140002EE9
0x140002eca  mov     eax, [rbx+rcx*8+8]
0x140002ece  cmp     rbp, rax
0x140002ed1  jnb     short loc_140002EE9
0x140002ed3  mov     eax, [rbx+r9*8+10h]
0x140002ed8  cmp     [rbx+rcx*8+10h], eax
0x140002edc  jnz     short loc_140002EE9
0x140002ede  mov     eax, [rbx+r9*8+0Ch]
0x140002ee3  cmp     [rbx+rcx*8+0Ch], eax
0x140002ee7  jz      short loc_140002EF0
0x140002ee9  inc     edx
0x140002eeb  cmp     edx, r8d
0x140002eee  jb      short loc_140002EBC
0x140002ef0  cmp     edx, [rbx]
0x140002ef2  jnz     short loc_140002F3C
0x140002ef4  mov     eax, edi
0x140002ef6  inc     rax
0x140002ef9  mov     ecx, edi
0x140002efb  add     rax, rax
0x140002efe  add     rcx, rcx
0x140002f01  cmp     dword ptr [rbx+rax*8], 0
0x140002f05  jz      short loc_140002F17
0x140002f07  mov     eax, [rbx+rax*8]
0x140002f0a  cmp     rbp, rax
0x140002f0d  jnz     short loc_140002F2E
0x140002f0f  test    byte ptr [rsi+4], 20h
0x140002f13  jnz     short loc_140002F3C
0x140002f15  jmp     short loc_140002F2E
0x140002f17  lea     eax, [rdi+1]
0x140002f1a  mov     rdx, r13
0x140002f1d  mov     [r15+48h], eax
0x140002f21  mov     r8d, [rbx+rcx*8+0Ch]
0x140002f26  mov     cl, 1
0x140002f28  add     r8, r12
0x140002f2b  call    r8
0x140002f2e  inc     edi
0x140002f30  mov     r8d, [rbx]
0x140002f33  cmp     edi, r8d
0x140002f36  jb      loc_140002E91
0x140002f3c  mov     eax, 1
0x140002f41  lea     r11, [rsp+68h+var_28]
0x140002f46  mov     rbx, [r11+30h]
0x140002f4a  mov     rbp, [r11+38h]
0x140002f4e  mov     rsi, [r11+40h]
0x140002f52  mov     rsp, r11
0x140002f55  pop     r15
0x140002f57  pop     r14
0x140002f59  pop     r13
0x140002f5b  pop     r12
0x140002f5d  pop     rdi
0x140002f5e  retn
```
