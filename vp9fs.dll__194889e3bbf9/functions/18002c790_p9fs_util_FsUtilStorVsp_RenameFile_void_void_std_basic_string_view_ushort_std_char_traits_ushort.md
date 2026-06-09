# p9fs::util::FsUtilStorVsp::RenameFile(void *,void *,std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18002c790`
- end: `0x18002c8bc`
- name: `?RenameFile@FsUtilStorVsp@util@p9fs@@UEAAJPEAX0V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180004120`
- `0x180004c98`
- `0x18000d498`
- `0x18000e23c`
- `0x18001d8b4`
- `0x18002a63c`
- `0x18002c790`

## import_xrefs

- `lxutil!LxUtilFsCreateRenameInformation` at `0x18002c839`
- `lxutil!LxUtilFsCreateRenameInformation` at `0x18002c839`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall p9fs::util::FsUtilStorVsp::RenameFile(__int64 a1, __int64 a2, p9fs::util::storvsp *a3, _QWORD *a4)
{
  __int64 v7; // r8
  __int64 v8; // rax
  int v9; // esi
  unsigned int v10; // edi
  _QWORD *v11; // rbx
  unsigned int v12; // r9d
  __int64 result; // rax
  void *v14[2]; // [rsp+30h] [rbp-78h] BYREF
  __int64 v15; // [rsp+40h] [rbp-68h]
  __int128 pExceptionObject; // [rsp+48h] [rbp-60h] BYREF
  __int64 v17; // [rsp+58h] [rbp-50h]
  _WORD v18[2]; // [rsp+60h] [rbp-48h] BYREF
  int v19; // [rsp+64h] [rbp-44h]
  __int64 v20; // [rsp+68h] [rbp-40h]

  v7 = *a4;
  v8 = 2LL * a4[1];
  if ( (unsigned __int16)v8 != v8 )
  {
    pExceptionObject = 0;
    v17 = 0;
    gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  try
  {
    v18[0] = 2 * *((_WORD *)a4 + 4);
    v18[1] = v8;
    v19 = 0;
    v20 = v7;
    v9 = (unsigned __int16)v8 + 20;
    v10 = (unsigned __int16)v8 + 44;
    *(_OWORD *)v14 = 0;
    v15 = 0;
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v14, v10);
    v11 = v14[0];
    *(_DWORD *)v14[0] = 1;
    v11[1] = a2;
    *((_DWORD *)v11 + 5) = v9;
    LxUtilFsCreateRenameInformation(0, v18, *(_QWORD *)(a1 + 8), 0, v11 + 3, v11 + 2);
    LODWORD(v11) = p9fs::util::storvsp::SetInformationFile(
                     a3,
                     v11,
                     (struct _VSTOR_VSMB_SET_INFORMATION_FILE_REQUEST *)v10,
                     v12);
    std::vector<unsigned char>::~vector<unsigned char>(v14);
    result = (unsigned int)v11;
  }
  catch ( ... )
  {
    std::vector<unsigned char>::~vector<unsigned char>(v14);
    return 4294967284LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002c790  mov     r11, rsp
0x18002c793  mov     [r11+10h], rbx
0x18002c797  push    rsi
0x18002c798  push    rdi
0x18002c799  push    r12
0x18002c79b  push    r14
0x18002c79d  push    r15
0x18002c79f  sub     rsp, 80h
0x18002c7a6  mov     rax, cs:__security_cookie
0x18002c7ad  xor     rax, rsp
0x18002c7b0  mov     [rsp+0A8h+var_38], rax
0x18002c7b5  mov     r12, r8
0x18002c7b8  mov     r14, rdx
0x18002c7bb  mov     r15, rcx
0x18002c7be  mov     r8, [r9]
0x18002c7c1  mov     rax, [r9+8]
0x18002c7c5  add     rax, rax
0x18002c7c8  movzx   ecx, ax
0x18002c7cb  cmp     rcx, rax
0x18002c7ce  jnz     loc_18002C891
0x18002c7d4  xor     eax, eax
0x18002c7d6  mov     [rsp+0A8h+var_48], cx
0x18002c7db  mov     [rsp+0A8h+var_46], cx
0x18002c7e0  mov     [rsp+0A8h+var_44], eax
0x18002c7e4  mov     [r11-40h], r8
0x18002c7e8  lea     esi, [rcx+14h]
0x18002c7eb  lea     edi, [rsi+18h]
0x18002c7ee  xorps   xmm1, xmm1
0x18002c7f1  movdqu  xmmword ptr [rsp+0A8h+var_78], xmm1
0x18002c7f7  mov     [r11-68h], rax
0x18002c7fb  mov     edx, edi
0x18002c7fd  lea     rcx, [r11-78h]
0x18002c801  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002c806  nop
0x18002c807  mov     rbx, [rsp+0A8h+var_78]
0x18002c80c  mov     dword ptr [rbx], 1
0x18002c812  mov     [rbx+8], r14
0x18002c816  mov     [rbx+14h], esi
0x18002c819  lea     rax, [rbx+10h]
0x18002c81d  lea     r9, [rbx+18h]
0x18002c821  mov     [rsp+0A8h+var_80], rax
0x18002c826  mov     [rsp+0A8h+var_88], r9
0x18002c82b  xor     r9d, r9d
0x18002c82e  mov     r8, [r15+8]
0x18002c832  lea     rdx, [rsp+0A8h+var_48]
0x18002c837  xor     ecx, ecx
0x18002c839  call    cs:__imp_LxUtilFsCreateRenameInformation
0x18002c83f  mov     r8d, edi; struct _VSTOR_VSMB_SET_INFORMATION_FILE_REQUEST *
0x18002c842  mov     rdx, rbx; void *
0x18002c845  mov     rcx, r12; this
0x18002c848  call    ?SetInformationFile@storvsp@util@p9fs@@YAJPEAXPEAU_VSTOR_VSMB_SET_INFORMATION_FILE_REQUEST@@K@Z; p9fs::util::storvsp::SetInformationFile(void *,_VSTOR_VSMB_SET_INFORMATION_FILE_REQUEST *,ulong)
0x18002c84d  mov     ebx, eax
0x18002c84f  lea     rcx, [rsp+0A8h+var_78]
0x18002c854  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002c859  mov     eax, ebx
0x18002c85b  mov     rcx, [rsp+0A8h+var_38]
0x18002c860  xor     rcx, rsp; StackCookie
0x18002c863  call    __security_check_cookie
0x18002c868  mov     rbx, [rsp+0A8h+arg_8]
0x18002c870  add     rsp, 80h
0x18002c877  pop     r15
0x18002c879  pop     r14
0x18002c87b  pop     r12
0x18002c87d  pop     rdi
0x18002c87e  pop     rsi
0x18002c87f  retn
0x18002c880  lea     rcx, [rsp+0A8h+var_78]
0x18002c885  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002c88a  mov     eax, 0FFFFFFF4h
0x18002c88f  jmp     short loc_18002C85B
0x18002c891  xorps   xmm0, xmm0
0x18002c894  xor     eax, eax
0x18002c896  movups  [rsp+0A8h+pExceptionObject], xmm0
0x18002c89b  mov     [rsp+0A8h+var_50], rax
0x18002c8a0  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x18002c8a5  call    ??0narrowing_error@gsl@@QEAA@XZ; gsl::narrowing_error::narrowing_error(void)
0x18002c8aa  lea     rdx, _TI2?AUnarrowing_error@gsl@@; pThrowInfo
0x18002c8b1  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18002c8b6  call    _CxxThrowException_0
```
