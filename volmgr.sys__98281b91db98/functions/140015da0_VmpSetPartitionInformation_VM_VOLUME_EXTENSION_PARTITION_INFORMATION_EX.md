# VmpSetPartitionInformation(VM_VOLUME_EXTENSION *,_PARTITION_INFORMATION_EX *)

- ea: `0x140015da0`
- end: `0x140015f64`
- name: `?VmpSetPartitionInformation@@YAXPEAVVM_VOLUME_EXTENSION@@PEAU_PARTITION_INFORMATION_EX@@@Z`
- size: `452`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *, struct _PARTITION_INFORMATION_EX *)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000e010`
- `0x14000f3b0`
- `0x140016130`
- `0x140016540`

## callees

- `0x140003c50`
- `0x140005050`
- `0x140005540`
- `0x14000f6fc`
- `0x14000fd48`
- `0x140015c30`
- `0x140015da0`

## pseudocode

```c
void __fastcall VmpSetPartitionInformation(struct VM_VOLUME_EXTENSION *a1, struct _PARTITION_INFORMATION_EX *a2)
{
  char v4; // bp
  char v5; // r14
  char v6; // r15
  __int64 v7; // rax
  __int128 v8; // xmm0
  LARGE_INTEGER StartingOffset; // rax
  _QWORD v10[14]; // [rsp+20h] [rbp-D8h] BYREF
  unsigned __int16 v11; // [rsp+90h] [rbp-68h] BYREF
  unsigned __int8 v12[54]; // [rsp+92h] [rbp-66h] BYREF

  v4 = a2->PartitionStyle == PARTITION_STYLE_GPT;
  if ( *((_BYTE *)a1 + 424) == v4 )
  {
    StartingOffset = a2->StartingOffset;
    v5 = 0;
    if ( *((_QWORD *)a1 + 49) == StartingOffset.QuadPart && *((_QWORD *)a1 + 50) == StartingOffset.QuadPart )
      return;
  }
  else
  {
    v5 = 1;
  }
  v6 = 0;
  if ( a2->PartitionStyle == PARTITION_STYLE_GPT )
  {
    v7 = *(_QWORD *)&a2->Mbr - *(_QWORD *)&PARTITION_SYSTEM_GUID.Data1;
    if ( !v7 )
      v7 = *(_QWORD *)a2->Gpt.PartitionType.Data4 - *(_QWORD *)PARTITION_SYSTEM_GUID.Data4;
    if ( !v7 )
      v6 = 1;
  }
  memset(v10, 0, 0x68u);
  v8 = *(_OWORD *)((char *)a1 + 408);
  LOBYTE(v10[0]) = *((_BYTE *)a1 + 426);
  v10[1] = *((_QWORD *)a1 + 43);
  v10[2] = *((_QWORD *)a1 + 45);
  v10[3] = *((_QWORD *)a1 + 46);
  LODWORD(v10[4]) = *((_DWORD *)a1 + 96);
  v10[5] = *((_QWORD *)a1 + 47);
  LODWORD(v10[6]) = *((_DWORD *)a1 + 97);
  v10[7] = a2->StartingOffset.QuadPart;
  v10[8] = a2->PartitionLength.QuadPart;
  v10[12] = *((_QWORD *)a1 + 54);
  *(_OWORD *)&v10[9] = v8;
  LOBYTE(v10[11]) = v4;
  BYTE1(v10[11]) = v6;
  VmpZeroRefCallback(a1, VmpSetTargetCallback, v10);
  if ( v5 )
  {
    if ( v6 )
      VmpApplyEspProtection(a1);
    v11 = 48;
    if ( VmpQueryUniqueIdInternal(a1, &v11, v12) >= 0 )
      VmpNotify(a1, &GUID_IO_VOLUME_UNIQUE_ID_CHANGE, v11 + 2, &v11);
  }
}

```

## disassembly

```asm
0x140015da0  push    rbx
0x140015da2  push    rbp
0x140015da3  push    rsi
0x140015da4  push    rdi
0x140015da5  push    r14
0x140015da7  sub     rsp, 0D0h
0x140015dae  mov     rax, cs:__security_cookie
0x140015db5  xor     rax, rsp
0x140015db8  mov     [rsp+0F8h+var_30], rax
0x140015dc0  mov     rbx, rcx
0x140015dc3  mov     rdi, rdx
0x140015dc6  mov     ecx, [rdx]
0x140015dc8  cmp     ecx, 1
0x140015dcb  setz    bpl
0x140015dcf  cmp     [rbx+1A8h], bpl
0x140015dd6  jz      loc_140015F42
0x140015ddc  mov     r14b, 1
0x140015ddf  mov     [rsp+0F8h+arg_10], r15
0x140015de7  xor     r15b, r15b
0x140015dea  cmp     ecx, 1
0x140015ded  jnz     short loc_140015E0F
0x140015def  mov     rax, [rdx+20h]
0x140015df3  sub     rax, qword ptr cs:PARTITION_SYSTEM_GUID.Data1
0x140015dfa  jnz     short loc_140015E07
0x140015dfc  mov     rax, [rdx+28h]
0x140015e00  sub     rax, qword ptr cs:PARTITION_SYSTEM_GUID.Data4
0x140015e07  test    rax, rax
0x140015e0a  jnz     short loc_140015E0F
0x140015e0c  mov     r15b, 1
0x140015e0f  xor     edx, edx; Val
0x140015e11  lea     rcx, [rsp+0F8h+var_D8]; void *
0x140015e16  mov     r8d, 68h ; 'h'; Size
0x140015e1c  call    memset
0x140015e21  movzx   eax, byte ptr [rbx+1AAh]
0x140015e28  lea     r8, [rsp+0F8h+var_D8]; void *
0x140015e2d  movups  xmm0, xmmword ptr [rbx+198h]
0x140015e34  mov     [rsp+0F8h+var_D8], al
0x140015e38  lea     rdx, ?VmpSetTargetCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z; int (*)(struct VM_VOLUME_EXTENSION *, void *)
0x140015e3f  mov     rax, [rbx+158h]
0x140015e46  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140015e49  mov     [rsp+0F8h+var_D0], rax
0x140015e4e  mov     rax, [rbx+168h]
0x140015e55  mov     [rsp+0F8h+var_C8], rax
0x140015e5a  mov     rax, [rbx+170h]
0x140015e61  mov     [rsp+0F8h+var_C0], rax
0x140015e66  mov     eax, [rbx+180h]
0x140015e6c  mov     [rsp+0F8h+var_B8], eax
0x140015e70  mov     rax, [rbx+178h]
0x140015e77  mov     [rsp+0F8h+var_B0], rax
0x140015e7c  mov     eax, [rbx+184h]
0x140015e82  mov     [rsp+0F8h+var_A8], eax
0x140015e86  mov     rax, [rdi+8]
0x140015e8a  mov     [rsp+0F8h+var_A0], rax
0x140015e8f  mov     rax, [rdi+10h]
0x140015e93  mov     [rsp+0F8h+var_98], rax
0x140015e98  mov     rax, [rbx+1B0h]
0x140015e9f  mov     [rsp+0F8h+var_78], rax
0x140015ea7  movups  [rsp+0F8h+var_90], xmm0
0x140015eac  mov     [rsp+0F8h+var_80], bpl
0x140015eb1  mov     [rsp+0F8h+var_7F], r15b
0x140015eb6  call    ?VmpZeroRefCallback@@YAJPEAVVM_VOLUME_EXTENSION@@P6AJ0PEAX@Z1@Z; VmpZeroRefCallback(VM_VOLUME_EXTENSION *,long (*)(VM_VOLUME_EXTENSION *,void *),void *)
0x140015ebb  test    r14b, r14b
0x140015ebe  jz      short loc_140015F1B
0x140015ec0  test    r15b, r15b
0x140015ec3  jz      short loc_140015ECD
0x140015ec5  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140015ec8  call    ?VmpApplyEspProtection@@YAJPEAVVM_VOLUME_EXTENSION@@@Z; VmpApplyEspProtection(VM_VOLUME_EXTENSION *)
0x140015ecd  mov     eax, 30h ; '0'
0x140015ed2  lea     r8, [rsp+0F8h+var_66]; unsigned __int8 *
0x140015eda  lea     rdx, [rsp+0F8h+var_68]; unsigned __int16 *
0x140015ee2  mov     [rsp+0F8h+var_68], ax
0x140015eea  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140015eed  call    ?VmpQueryUniqueIdInternal@@YAJPEAVVM_VOLUME_EXTENSION@@PEAGPEAE@Z; VmpQueryUniqueIdInternal(VM_VOLUME_EXTENSION *,ushort *,uchar *)
0x140015ef2  test    eax, eax
0x140015ef4  js      short loc_140015F1B
0x140015ef6  movzx   r8d, [rsp+0F8h+var_68]
0x140015eff  lea     r9, [rsp+0F8h+var_68]; void *
0x140015f07  add     r8w, 2; unsigned __int16
0x140015f0c  lea     rdx, GUID_IO_VOLUME_UNIQUE_ID_CHANGE; struct _GUID *
0x140015f13  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140015f16  call    ?VmpNotify@@YAXPEAVVM_VOLUME_EXTENSION@@PEBU_GUID@@GPEAX@Z; VmpNotify(VM_VOLUME_EXTENSION *,_GUID const *,ushort,void *)
0x140015f1b  mov     r15, [rsp+0F8h+arg_10]
0x140015f23  mov     rcx, [rsp+0F8h+var_30]
0x140015f2b  xor     rcx, rsp; StackCookie
0x140015f2e  call    __security_check_cookie
0x140015f33  add     rsp, 0D0h
0x140015f3a  pop     r14
0x140015f3c  pop     rdi
0x140015f3d  pop     rsi
0x140015f3e  pop     rbp
0x140015f3f  pop     rbx
0x140015f40  retn
0x140015f42  mov     rax, [rdx+8]
0x140015f46  xor     r14b, r14b
0x140015f49  cmp     [rbx+188h], rax
0x140015f50  jnz     loc_140015DDF
0x140015f56  cmp     [rbx+190h], rax
0x140015f5d  jz      short loc_140015F23
0x140015f5f  jmp     loc_140015DDF
```
