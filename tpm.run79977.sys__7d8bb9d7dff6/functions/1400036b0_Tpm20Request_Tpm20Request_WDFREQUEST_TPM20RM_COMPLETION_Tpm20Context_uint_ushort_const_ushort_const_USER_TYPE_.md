# Tpm20Request::Tpm20Request(WDFREQUEST__ *,_TPM20RM_COMPLETION *,Tpm20Context *,uint,ushort const *,ushort const *,_USER_TYPE,void *,uint,void *,uint,void *,_TPM20_CMD_HEADER)

- ea: `0x1400036b0`
- end: `0x1400037bf`
- name: `??0Tpm20Request@@AEAA@PEAUWDFREQUEST__@@PEAU_TPM20RM_COMPLETION@@PEAVTpm20Context@@IPEBG3W4_USER_TYPE@@PEAXI5I5U_TPM20_CMD_HEADER@@@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400034a8`

## callees

- `0x140039b40`

## pseudocode

```c
__int64 __fastcall Tpm20Request::Tpm20Request(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9,
        int a10,
        __int64 a11,
        int a12,
        __int64 a13,
        __int64 a14)
{
  __int64 v15; // rdx
  __int16 v16; // ax
  __int64 v17; // rax
  void *v18; // rcx

  *(_QWORD *)(a1 + 24) = a9;
  *(_DWORD *)(a1 + 176) = a5;
  *(_DWORD *)(a1 + 180) = a10;
  *(_DWORD *)(a1 + 184) = a12;
  *(_QWORD *)(a1 + 232) = a6;
  *(_QWORD *)(a1 + 240) = a7;
  *(_DWORD *)(a1 + 280) = a8;
  *(_QWORD *)(a1 + 216) = a2;
  v15 = a11;
  *(_QWORD *)(a1 + 16) = a4;
  v16 = *(_WORD *)(a14 + 8);
  *(_QWORD *)a1 = *(_QWORD *)a14;
  *(_WORD *)(a1 + 8) = v16;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_DWORD *)(a1 + 188) = 0;
  *(_QWORD *)(a1 + 192) = 2431;
  *(_QWORD *)(a1 + 200) = 0;
  *(_DWORD *)(a1 + 208) = 16;
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 224) = a3;
  v17 = a13;
  if ( !a13 )
    v17 = a11;
  v18 = (void *)(a1 + 48);
  if ( !a13 )
    v15 = 0;
  *(_QWORD *)(a1 + 32) = v17;
  *(_QWORD *)(a1 + 248) = v15;
  memset(v18, 0, 0x78u);
  *(_QWORD *)(a1 + 272) = MEMORY[0xFFFFF78000000014];
  return a1;
}

```

## disassembly

```asm
0x1400036b0  push    rbx
0x1400036b2  sub     rsp, 20h
0x1400036b6  mov     rax, [rsp+28h+arg_40]
0x1400036bb  mov     rbx, rcx
0x1400036be  mov     [rcx+18h], rax
0x1400036c2  mov     eax, [rsp+28h+arg_20]
0x1400036c6  mov     [rcx+0B0h], eax
0x1400036cc  mov     eax, [rsp+28h+arg_48]
0x1400036d0  mov     [rcx+0B4h], eax
0x1400036d6  mov     eax, [rsp+28h+arg_58]
0x1400036dd  mov     [rcx+0B8h], eax
0x1400036e3  mov     rax, [rsp+28h+arg_28]
0x1400036e8  mov     [rcx+0E8h], rax
0x1400036ef  mov     rax, [rsp+28h+arg_30]
0x1400036f4  mov     [rcx+0F0h], rax
0x1400036fb  mov     eax, [rsp+28h+arg_38]
0x1400036ff  mov     [rcx+118h], eax
0x140003705  mov     rax, [rsp+28h+arg_68]
0x14000370d  mov     [rcx+0D8h], rdx
0x140003714  mov     rdx, [rsp+28h+arg_50]
0x14000371c  mov     [rcx+10h], r9
0x140003720  xor     r9d, r9d
0x140003723  movsd   xmm0, qword ptr [rax]
0x140003727  movzx   eax, word ptr [rax+8]
0x14000372b  movsd   qword ptr [rcx], xmm0
0x14000372f  mov     [rcx+8], ax
0x140003733  mov     [rcx+28h], r9
0x140003737  mov     [rcx+0A8h], r9
0x14000373e  mov     [rcx+0BCh], r9d
0x140003745  mov     qword ptr [rcx+0C0h], 97Fh
0x140003750  mov     [rcx+0C8h], r9
0x140003757  mov     dword ptr [rcx+0D0h], 10h
0x140003761  mov     [rcx+110h], r9
0x140003768  mov     rcx, [rsp+28h+arg_60]
0x140003770  test    rcx, rcx
0x140003773  mov     [rbx+0E0h], r8
0x14000377a  mov     rax, rcx
0x14000377d  mov     r8d, 78h ; 'x'; Size
0x140003783  cmovz   rax, rdx
0x140003787  lea     rcx, [rbx+30h]; void *
0x14000378b  cmovz   rdx, r9
0x14000378f  mov     [rbx+20h], rax
0x140003793  mov     [rbx+0F8h], rdx
0x14000379a  xor     edx, edx; Val
0x14000379c  call    memset
0x1400037a1  mov     rax, 0FFFFF78000000014h
0x1400037ab  mov     rax, [rax]
0x1400037ae  mov     [rbx+110h], rax
0x1400037b5  mov     rax, rbx
0x1400037b8  add     rsp, 20h
0x1400037bc  pop     rbx
0x1400037bd  retn
```
