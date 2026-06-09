# Tpm20NVRead(Tpm20Context *,TpmStack *,uint,uchar *,uint *,TPM2B_BUFFER const *)

- ea: `0x14002a410`
- end: `0x14002a522`
- name: `?Tpm20NVRead@@YAJPEAVTpm20Context@@PEAVTpmStack@@IPEAEPEAIPEBVTPM2B_BUFFER@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(struct Tpm20Context *, struct TpmStack *, unsigned int, unsigned __int8 *, unsigned int *, const struct TPM2B_BUFFER *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14002d050`

## callees

- `0x1400078b8`
- `0x14001ac60`
- `0x140029100`
- `0x14002a410`
- `0x140033154`
- `0x140033400`
- `0x140039740`

## pseudocode

```c
__int64 __fastcall Tpm20NVRead(
        struct Tpm20Context *a1,
        struct TpmStack *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        const void **a6)
{
  int NV; // eax
  _QWORD v10[3]; // [rsp+30h] [rbp-68h] BYREF
  __int128 v11; // [rsp+48h] [rbp-50h] BYREF
  int v12; // [rsp+58h] [rbp-40h]

  v10[0] = 0;
  v10[1] = a2;
  v10[2] = a1;
  v12 = 0;
  v11 = 0;
  if ( !a5 )
    return 3221225485LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
  if ( a6 )
    memcpy_s(&v11, 0x14u, a6[1], *(unsigned __int16 *)a6);
  if ( dword_1400480C8 == 1 )
  {
    NV = Tpm12ApiOwnerReadNV((struct HTPMCONTEXT__ *)v10, a3, (const struct _TPM_API_HASH_DATA *)&v11, a5, a4);
  }
  else if ( dword_1400480C8 == 2 )
  {
    NV = TpmW8ApiOwnerReadNV((struct HTPMCONTEXT__ *)v10, a3, (const struct _TPM_API_HASH_DATA *)&v11, a5, a4);
  }
  else
  {
    NV = -2144796371;
  }
  return HRESULTToNTSTATUS(NV);
}

```

## disassembly

```asm
0x14002a410  push    rbx
0x14002a412  push    rbp
0x14002a413  push    rsi
0x14002a414  push    rdi
0x14002a415  sub     rsp, 78h
0x14002a419  mov     rax, cs:__security_cookie
0x14002a420  xor     rax, rsp
0x14002a423  mov     [rsp+98h+var_38], rax
0x14002a428  mov     rdi, [rsp+98h+arg_20]
0x14002a430  xor     eax, eax
0x14002a432  mov     rbx, [rsp+98h+arg_28]
0x14002a43a  xorps   xmm0, xmm0
0x14002a43d  mov     [rsp+98h+var_68], 0
0x14002a446  mov     rbp, r9
0x14002a449  mov     [rsp+98h+var_60], rdx
0x14002a44e  mov     esi, r8d
0x14002a451  mov     [rsp+98h+var_58], rcx
0x14002a456  mov     [rsp+98h+var_40], eax
0x14002a45a  movups  [rsp+98h+var_50], xmm0
0x14002a45f  test    rdi, rdi
0x14002a462  jnz     short loc_14002A46E
0x14002a464  mov     eax, 0C000000Dh
0x14002a469  jmp     loc_14002A50B
0x14002a46e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a475  lea     rax, WPP_GLOBAL_Control
0x14002a47c  cmp     rcx, rax
0x14002a47f  jz      short loc_14002A49D
0x14002a481  mov     eax, [rcx+2Ch]
0x14002a484  test    al, 4
0x14002a486  jz      short loc_14002A49D
0x14002a488  mov     rcx, [rcx+18h]
0x14002a48c  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14002a493  mov     edx, 42h ; 'B'
0x14002a498  call    WPP_SF_
0x14002a49d  test    rbx, rbx
0x14002a4a0  jz      short loc_14002A4B9
0x14002a4a2  movzx   r9d, word ptr [rbx]; MaxCount
0x14002a4a6  lea     rcx, [rsp+98h+var_50]; void *
0x14002a4ab  mov     r8, [rbx+8]; Src
0x14002a4af  mov     edx, 14h; DstSize
0x14002a4b4  call    memcpy_s
0x14002a4b9  mov     eax, cs:dword_1400480C8
0x14002a4bf  cmp     eax, 1
0x14002a4c2  jnz     short loc_14002A4DF
0x14002a4c4  mov     r9, rdi; unsigned int *
0x14002a4c7  mov     [rsp+98h+var_78], rbp; unsigned __int8 *
0x14002a4cc  lea     r8, [rsp+98h+var_50]; struct _TPM_API_HASH_DATA *
0x14002a4d1  mov     edx, esi; unsigned int
0x14002a4d3  lea     rcx, [rsp+98h+var_68]; struct HTPMCONTEXT__ *
0x14002a4d8  call    ?Tpm12ApiOwnerReadNV@@YAJPEAUHTPMCONTEXT__@@IPEBU_TPM_API_HASH_DATA@@PEAIPEAE@Z; Tpm12ApiOwnerReadNV(HTPMCONTEXT__ *,uint,_TPM_API_HASH_DATA const *,uint *,uchar *)
0x14002a4dd  jmp     short loc_14002A504
0x14002a4df  cmp     eax, 2
0x14002a4e2  jnz     short loc_14002A4FF
0x14002a4e4  mov     r9, rdi; unsigned int *
0x14002a4e7  mov     [rsp+98h+var_78], rbp; unsigned __int8 *
0x14002a4ec  lea     r8, [rsp+98h+var_50]; struct _TPM_API_HASH_DATA *
0x14002a4f1  mov     edx, esi; unsigned int
0x14002a4f3  lea     rcx, [rsp+98h+var_68]; struct HTPMCONTEXT__ *
0x14002a4f8  call    ?TpmW8ApiOwnerReadNV@@YAJPEAUHTPMCONTEXT__@@IPEBU_TPM_API_HASH_DATA@@PEAIPEAE@Z; TpmW8ApiOwnerReadNV(HTPMCONTEXT__ *,uint,_TPM_API_HASH_DATA const *,uint *,uchar *)
0x14002a4fd  jmp     short loc_14002A504
0x14002a4ff  mov     eax, 8029012Dh
0x14002a504  mov     ecx, eax; int
0x14002a506  call    ?HRESULTToNTSTATUS@@YAJJ@Z; HRESULTToNTSTATUS(long)
0x14002a50b  mov     rcx, [rsp+98h+var_38]
0x14002a510  xor     rcx, rsp; StackCookie
0x14002a513  call    __security_check_cookie
0x14002a518  add     rsp, 78h
0x14002a51c  pop     rdi
0x14002a51d  pop     rsi
0x14002a51e  pop     rbp
0x14002a51f  pop     rbx
0x14002a520  retn
```
