# CLogFile::OpenExistingFile(ushort const *)

- ea: `0x180009720`
- end: `0x1800097f8`
- name: `?OpenExistingFile@CLogFile@@MEAA?AW4RCF_RESULT@@PEBG@Z`
- size: `216`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800015f0`
- `0x180009720`
- `0x180009800`
- `0x1800098bc`
- `0x18000997c`
- `0x180009ce8`
- `0x180009ecc`
- `0x180009f14`
- `0x18000ed1c`

## pseudocode

```c
__int64 __fastcall CLogFile::OpenExistingFile(__int64 a1, const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  void **v6; // rsi
  int v7; // eax
  int v9; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  v4 = CheckVolumeWriteProtection(*(const unsigned __int16 **)(a1 + 40), &v9);
  if ( v4 < 0 )
    TrkRaiseNtStatus(v4);
  *(_DWORD *)(a1 + 32) &= ~1u;
  v5 = 1;
  *(_DWORD *)(a1 + 32) |= v9 & 1;
  v6 = (void **)(a1 + 16);
  v7 = CSecureFile::OpenExistingSecureFile((CSecureFile *)(a1 + 16), a2, -(*(_DWORD *)(a1 + 32) & 1));
  if ( v7 >= 0 )
  {
    CLogFile::SetOplock((CLogFile *)a1);
    CLogFileHeader::LoadHeader((CLogFileHeader *)(a1 + 80), *v6);
    *(_QWORD *)(a1 + 128) = *v6;
    CLogFile::GetSize((CLogFile *)a1);
    v5 = (unsigned int)CLogFile::Validate((CLogFile *)a1) != 0 ? 2 : 0;
  }
  else if ( v7 != -1073741772 && v7 != -1073741766 )
  {
    TrkRaiseNtStatus(v7);
  }
  if ( !v5 )
    CLogFile::CloseLog((CLogFile *)a1);
  return v5;
}

```

## disassembly

```asm
0x180009720  mov     rax, rsp
0x180009723  mov     [rax+10h], rbx
0x180009727  mov     [rax+8], rcx
0x18000972b  push    rsi
0x18000972c  push    rdi
0x18000972d  push    r14
0x18000972f  sub     rsp, 30h
0x180009733  mov     r14, rdx
0x180009736  mov     rbx, rcx
0x180009739  mov     dword ptr [rax-28h], 2
0x180009740  mov     dword ptr [rax+18h], 0
0x180009747  lea     rdx, [rax+18h]; int *
0x18000974b  mov     rcx, [rcx+28h]; unsigned __int16 *
0x18000974f  call    ?CheckVolumeWriteProtection@@YAJPEBGPEAH@Z; CheckVolumeWriteProtection(ushort const *,int *)
0x180009754  test    eax, eax
0x180009756  jns     short loc_18000975F
0x180009758  mov     ecx, eax; int
0x18000975a  call    ?TrkRaiseNtStatus@@YAXJ@Z; TrkRaiseNtStatus(long)
0x18000975f  and     dword ptr [rbx+20h], 0FFFFFFFEh
0x180009763  mov     eax, [rsp+48h+arg_10]
0x180009767  mov     edi, 1
0x18000976c  and     eax, edi
0x18000976e  or      [rbx+20h], eax
0x180009771  mov     r8d, [rbx+20h]
0x180009775  lea     rsi, [rbx+10h]
0x180009779  shr     r8d, 1
0x18000977c  sbb     r8d, r8d; int
0x18000977f  mov     rdx, r14; unsigned __int16 *
0x180009782  mov     rcx, rsi; this
0x180009785  call    ?OpenExistingSecureFile@CSecureFile@@QEAAJPEBGH@Z; CSecureFile::OpenExistingSecureFile(ushort const *,int)
0x18000978a  test    eax, eax
0x18000978c  jns     short loc_1800097A3
0x18000978e  cmp     eax, 0C0000034h
0x180009793  jz      short loc_1800097D8
0x180009795  cmp     eax, 0C000003Ah
0x18000979a  jz      short loc_1800097D8
0x18000979c  mov     ecx, eax; int
0x18000979e  call    ?TrkRaiseNtStatus@@YAXJ@Z; TrkRaiseNtStatus(long)
0x1800097a3  mov     rcx, rbx; this
0x1800097a6  call    ?SetOplock@CLogFile@@QEAAXXZ; CLogFile::SetOplock(void)
0x1800097ab  lea     rcx, [rbx+50h]; this
0x1800097af  mov     rdx, [rsi]; void *
0x1800097b2  call    ?LoadHeader@CLogFileHeader@@AEAAXPEAX@Z; CLogFileHeader::LoadHeader(void *)
0x1800097b7  mov     rax, [rsi]
0x1800097ba  mov     [rbx+80h], rax
0x1800097c1  mov     rcx, rbx; this
0x1800097c4  call    ?GetSize@CLogFile@@AEAAXXZ; CLogFile::GetSize(void)
0x1800097c9  mov     rcx, rbx; this
0x1800097cc  call    ?Validate@CLogFile@@AEAAHXZ; CLogFile::Validate(void)
0x1800097d1  neg     eax
0x1800097d3  sbb     edi, edi
0x1800097d5  and     edi, 2
0x1800097d8  mov     [rsp+48h+var_28], edi
0x1800097dc  test    edi, edi
0x1800097de  jnz     short loc_1800097E8
0x1800097e0  mov     rcx, rbx; this
0x1800097e3  call    ?CloseLog@CLogFile@@AEAAXXZ; CLogFile::CloseLog(void)
0x1800097e8  mov     eax, edi
0x1800097ea  mov     rbx, [rsp+48h+arg_8]
0x1800097ef  add     rsp, 30h
0x1800097f3  pop     r14
0x1800097f5  pop     rdi
0x1800097f6  pop     rsi
0x1800097f7  retn
0x18001165b  push    rbp
0x18001165d  sub     rsp, 20h
0x180011661  mov     rbp, rdx
0x180011664  movzx   eax, cl
0x180011667  test    cl, cl
0x180011669  jnz     short loc_180011671
0x18001166b  cmp     dword ptr [rbp+20h], 0
0x18001166f  jnz     short loc_18001167B
0x180011671  mov     rcx, [rbp+50h]; this
0x180011675  call    ?CloseLog@CLogFile@@AEAAXXZ; CLogFile::CloseLog(void)
0x18001167a  nop
0x18001167b  add     rsp, 20h
0x18001167f  pop     rbp
0x180011680  retn
```
