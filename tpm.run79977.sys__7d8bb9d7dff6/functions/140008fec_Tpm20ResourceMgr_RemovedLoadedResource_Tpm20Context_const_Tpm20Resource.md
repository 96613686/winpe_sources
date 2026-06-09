# Tpm20ResourceMgr::RemovedLoadedResource(Tpm20Context const *,Tpm20Resource *)

- ea: `0x140008fec`
- end: `0x1400090ae`
- name: `?RemovedLoadedResource@Tpm20ResourceMgr@@AEAAXPEBVTpm20Context@@PEAVTpm20Resource@@@Z`
- size: `194`
- prototype: `void(Tpm20ResourceMgr *__hidden this, const struct Tpm20Context *, struct Tpm20Resource *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14000596c`
- `0x140006fac`
- `0x140007428`
- `0x1400086a4`
- `0x140008aac`
- `0x140008bfc`

## callees

- `0x140008fec`
- `0x1400091e4`
- `0x140009224`

## pseudocode

```c
void __fastcall Tpm20ResourceMgr::RemovedLoadedResource(
        Tpm20ResourceMgr *this,
        const struct Tpm20Context *a2,
        struct Tpm20Resource *a3)
{
  char *v3; // rax
  __int64 v5; // r8
  char **v7; // rcx
  struct Tpm20Resource **v8; // rdx
  struct Tpm20Resource **v9; // rcx
  struct Tpm20Resource *v10; // rcx
  struct Tpm20Resource **v11; // rax

  v3 = (char *)a3 + 32;
  *((_BYTE *)a3 + 60) = 0;
  *((_DWORD *)a3 + 12) = 1073741832;
  v5 = *((_QWORD *)a3 + 4);
  if ( *(char **)(v5 + 8) != v3 )
    goto LABEL_11;
  v7 = (char **)*((_QWORD *)v3 + 1);
  if ( *v7 != v3 )
    goto LABEL_11;
  *v7 = (char *)v5;
  *(_QWORD *)(v5 + 8) = v7;
  v8 = (struct Tpm20Resource **)*((_QWORD *)a3 + 2);
  if ( v8[1] != (struct Tpm20Resource *)((char *)a3 + 16)
    || (v9 = (struct Tpm20Resource **)*((_QWORD *)a3 + 3), *v9 != (struct Tpm20Resource *)((char *)a3 + 16))
    || (*v9 = (struct Tpm20Resource *)v8,
        v8[1] = (struct Tpm20Resource *)v9,
        v10 = *(struct Tpm20Resource **)a3,
        *(struct Tpm20Resource **)(*(_QWORD *)a3 + 8LL) != a3)
    || (v11 = (struct Tpm20Resource **)*((_QWORD *)a3 + 1), *v11 != a3) )
  {
LABEL_11:
    __fastfail(3u);
  }
  *v11 = v10;
  *((_QWORD *)v10 + 1) = v11;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      47,
      WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids,
      a2,
      *((_DWORD *)a3 + 13));
  Tpm20Resource::`scalar deleting destructor'(a3, (unsigned int)v8);
}

```

## disassembly

```asm
0x140008fec  push    rbx
0x140008fee  sub     rsp, 30h
0x140008ff2  lea     rax, [r8+20h]
0x140008ff6  mov     byte ptr [r8+3Ch], 0
0x140008ffb  mov     dword ptr [r8+30h], 40000008h
0x140009003  mov     rbx, r8
0x140009006  mov     r8, [rax]
0x140009009  mov     r9, rdx
0x14000900c  cmp     [r8+8], rax
0x140009010  jnz     loc_1400090A7
0x140009016  mov     rcx, [rax+8]
0x14000901a  cmp     [rcx], rax
0x14000901d  jnz     loc_1400090A7
0x140009023  mov     [rcx], r8
0x140009026  lea     rax, [rbx+10h]
0x14000902a  mov     [r8+8], rcx
0x14000902e  mov     rdx, [rax]; unsigned int
0x140009031  cmp     [rdx+8], rax
0x140009035  jnz     short loc_1400090A7
0x140009037  mov     rcx, [rax+8]
0x14000903b  cmp     [rcx], rax
0x14000903e  jnz     short loc_1400090A7
0x140009040  mov     [rcx], rdx
0x140009043  mov     [rdx+8], rcx
0x140009047  mov     rcx, [rbx]
0x14000904a  cmp     [rcx+8], rbx
0x14000904e  jnz     short loc_1400090A7
0x140009050  mov     rax, [rbx+8]
0x140009054  cmp     [rax], rbx
0x140009057  jnz     short loc_1400090A7
0x140009059  mov     [rax], rcx
0x14000905c  mov     [rcx+8], rax
0x140009060  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140009067  lea     rax, WPP_GLOBAL_Control
0x14000906e  cmp     rcx, rax
0x140009071  jnz     short loc_140009082
0x140009073  mov     rcx, rbx; this
0x140009076  call    ??_GTpm20Resource@@AEAAPEAXI@Z; Tpm20Resource::`scalar deleting destructor'(uint)
0x14000907b  add     rsp, 30h
0x14000907f  pop     rbx
0x140009080  retn
0x140009082  mov     eax, [rcx+2Ch]
0x140009085  test    al, 4
0x140009087  jz      short loc_140009073
0x140009089  mov     eax, [rbx+34h]
0x14000908c  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140009093  mov     rcx, [rcx+18h]
0x140009097  mov     edx, 2Fh ; '/'
0x14000909c  mov     [rsp+38h+var_18], eax
0x1400090a0  call    WPP_SF_qD
0x1400090a5  jmp     short loc_140009073
0x1400090a7  mov     ecx, 3
0x1400090ac  int     29h; Win8: RtlFailFast(ecx)
```
