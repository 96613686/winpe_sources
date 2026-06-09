# CAttachmentServices::_OpTrustedHandler(void)

- ea: `0x180010e3c`
- end: `0x180010f5d`
- name: `?_OpTrustedHandler@CAttachmentServices@@AEAAXXZ`
- size: `289`
- prototype: `void __fastcall(CAttachmentServices *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x18000d110`
- `0x18000f420`
- `0x18001143c`

## callees

- `0x180002d10`
- `0x180002e30`
- `0x180003020`
- `0x180003080`
- `0x180003f30`
- `0x180006844`
- `0x18000f388`
- `0x180010c18`
- `0x180010e3c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010e8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010e8e`

## pseudocode

```c
void __fastcall CAttachmentServices::_OpTrustedHandler(CAttachmentServices *this)
{
  CAttachmentServices *v2; // rcx
  unsigned int v3; // esi
  FARPROC ProcAddress; // rbp
  int v5; // ebx
  __int64 v6; // rbx
  const unsigned __int16 *Type; // rax
  unsigned int v8; // eax
  __int64 v9; // rcx
  int v10; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v11; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  if ( (unsigned int)CAttachmentServices::PushOp(this, 7, &v11) )
  {
    v3 = 2;
    if ( CAttachmentServices::_GetHandler(v2)
      && CAttachmentServices::_LoadFHC(this)
      && (ProcAddress = GetProcAddress(*((HMODULE *)this + 39), (LPCSTR)0x65)) != 0 )
    {
      v6 = *((_QWORD *)this + 12);
      v10 = 0;
      Type = CAttachmentServices::_GetType((LPCWSTR *)this);
      v5 = ((__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, __int64, int *))ProcAddress)(
             *((_QWORD *)this + 5),
             Type,
             v6,
             &v10);
      if ( v5 >= 0 )
      {
        switch ( v10 )
        {
          case 0:
            CAttachmentServices::_FreeHandler(this);
            goto LABEL_20;
          case 1:
            v8 = 6152;
            break;
          case 2:
            v8 = 6151;
            break;
          case 3:
            v8 = 6150;
            break;
          default:
            v3 = 3;
            v5 = -2147024891;
            goto LABEL_20;
        }
        if ( (*((_DWORD *)this + 54) != 3 || v8 < *((_DWORD *)this + 22)) && v8 != *((_DWORD *)this + 22) )
        {
          *((_DWORD *)this + 22) = v8;
          CAttachmentServices::OpReset(this, 8);
        }
      }
    }
    else
    {
      v5 = -2147467259;
    }
LABEL_20:
    CAttachmentServices::ReportResult(this, (unsigned int)v5, v3);
    CAttachmentServices::PopOp(v9, v11);
  }
}

```

## disassembly

```asm
0x180010e3c  mov     [rsp+arg_0], rbx
0x180010e41  push    rbp
0x180010e42  push    rsi
0x180010e43  push    rdi
0x180010e44  sub     rsp, 30h
0x180010e48  lea     r8, [rsp+48h+arg_10]
0x180010e4d  mov     [rsp+48h+arg_10], 0
0x180010e55  mov     edx, 7
0x180010e5a  mov     rdi, rcx
0x180010e5d  call    ?PushOp@CAttachmentServices@@AEAAHW4ATTACHMENT_OP@@PEAW42@@Z; CAttachmentServices::PushOp(ATTACHMENT_OP,ATTACHMENT_OP *)
0x180010e62  test    eax, eax
0x180010e64  jz      loc_180010F50
0x180010e6a  mov     esi, 2
0x180010e6f  call    ?_GetHandler@CAttachmentServices@@AEAAHXZ; CAttachmentServices::_GetHandler(void)
0x180010e74  test    eax, eax
0x180010e76  jz      short loc_180010E9C
0x180010e78  mov     rcx, rdi; this
0x180010e7b  call    ?_LoadFHC@CAttachmentServices@@AEAAHXZ; CAttachmentServices::_LoadFHC(void)
0x180010e80  test    eax, eax
0x180010e82  jz      short loc_180010E9C
0x180010e84  mov     rcx, [rdi+138h]; hModule
0x180010e8b  lea     edx, [rsi+63h]; lpProcName
0x180010e8e  call    cs:__imp_GetProcAddress
0x180010e94  mov     rbp, rax
0x180010e97  test    rax, rax
0x180010e9a  jnz     short loc_180010EA6
0x180010e9c  mov     ebx, 80004005h
0x180010ea1  jmp     loc_180010F3A
0x180010ea6  mov     rbx, [rdi+60h]
0x180010eaa  mov     rcx, rdi; this
0x180010ead  mov     [rsp+48h+arg_8], 0
0x180010eb5  call    ?_GetType@CAttachmentServices@@AEAAPEBGXZ; CAttachmentServices::_GetType(void)
0x180010eba  mov     rcx, [rdi+28h]
0x180010ebe  lea     r9, [rsp+48h+arg_8]
0x180010ec3  mov     rdx, rax
0x180010ec6  mov     r8, rbx
0x180010ec9  mov     rax, rbp
0x180010ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ed1  mov     ebx, eax
0x180010ed3  test    eax, eax
0x180010ed5  js      short loc_180010F3A
0x180010ed7  mov     edx, [rsp+48h+arg_8]
0x180010edb  test    edx, edx
0x180010edd  jz      short loc_180010F32
0x180010edf  sub     edx, 1
0x180010ee2  jz      short loc_180010F08
0x180010ee4  sub     edx, 1
0x180010ee7  jz      short loc_180010F01
0x180010ee9  cmp     edx, 1
0x180010eec  jz      short loc_180010EFA
0x180010eee  mov     esi, 3
0x180010ef3  mov     ebx, 80070005h
0x180010ef8  jmp     short loc_180010F3A
0x180010efa  mov     eax, 1806h
0x180010eff  jmp     short loc_180010F0D
0x180010f01  mov     eax, 1807h
0x180010f06  jmp     short loc_180010F0D
0x180010f08  mov     eax, 1808h
0x180010f0d  cmp     dword ptr [rdi+0D8h], 3
0x180010f14  jnz     short loc_180010F1B
0x180010f16  cmp     eax, [rdi+58h]
0x180010f19  jnb     short loc_180010F3A
0x180010f1b  cmp     eax, [rdi+58h]
0x180010f1e  jz      short loc_180010F3A
0x180010f20  mov     edx, 8
0x180010f25  mov     [rdi+58h], eax
0x180010f28  mov     rcx, rdi
0x180010f2b  call    ?OpReset@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::OpReset(ATTACHMENT_OP)
0x180010f30  jmp     short loc_180010F3A
0x180010f32  mov     rcx, rdi; this
0x180010f35  call    ?_FreeHandler@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_FreeHandler(void)
0x180010f3a  mov     r8d, esi
0x180010f3d  mov     edx, ebx
0x180010f3f  mov     rcx, rdi
0x180010f42  call    ?ReportResult@CAttachmentServices@@AEAAHJW4OP_RESULT@1@@Z; CAttachmentServices::ReportResult(long,CAttachmentServices::OP_RESULT)
0x180010f47  mov     edx, [rsp+48h+arg_10]
0x180010f4b  call    ?PopOp@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::PopOp(ATTACHMENT_OP)
0x180010f50  mov     rbx, [rsp+48h+arg_0]
0x180010f55  add     rsp, 30h
0x180010f59  pop     rdi
0x180010f5a  pop     rsi
0x180010f5b  pop     rbp
0x180010f5c  retn
```
