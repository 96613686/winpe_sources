# TpmResourceManager::DeleteResource(TpmResource *,bool)

- ea: `0x14001506c`
- end: `0x14001518c`
- name: `?DeleteResource@TpmResourceManager@@AEAAXPEAVTpmResource@@_N@Z`
- size: `288`
- prototype: `void __fastcall(TpmResourceManager *__hidden this, struct TpmResource *, bool)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e568`
- `0x140012abc`
- `0x1400135d0`
- `0x140013ab4`
- `0x14001506c`
- `0x140016014`
- `0x14001fcb4`

## callees

- `0x14001506c`
- `0x14001f030`
- `0x1400454a0`

## pseudocode

```c
void __fastcall TpmResourceManager::DeleteResource(TpmResourceManager *this, struct TpmResource *a2, char a3)
{
  struct TpmResource *i; // rax
  struct TpmResource **v7; // rax
  struct TpmResource **v8; // rcx
  char *v9; // rax
  char *v10; // rcx
  char **v11; // rdx

  if ( a2
    && a2 != (TpmResourceManager *)((char *)this + 40)
    && a2 != (TpmResourceManager *)((char *)this + 136)
    && a2 != (TpmResourceManager *)((char *)this + 232)
    && a2 != (TpmResourceManager *)((char *)this + 328)
    && a2 != (TpmResourceManager *)((char *)this + 424)
    && a2 != (TpmResourceManager *)((char *)this + 520)
    && a2 != (TpmResourceManager *)((char *)this + 616)
    && a2 != (TpmResourceManager *)((char *)this + 712) )
  {
    for ( i = (struct TpmResource *)*((_QWORD *)a2 + 8); i && a3; i = (struct TpmResource *)*((_QWORD *)a2 + 8) )
      TpmResourceManager::DeleteResource(this, i, 1);
    v7 = *(struct TpmResource ***)a2;
    if ( *(struct TpmResource **)a2 != a2 )
    {
      if ( v7[1] != a2 )
        goto LABEL_24;
      v8 = (struct TpmResource **)*((_QWORD *)a2 + 1);
      if ( *v8 != a2 )
        goto LABEL_24;
      *v8 = (struct TpmResource *)v7;
      v7[1] = (struct TpmResource *)v8;
    }
    v9 = (char *)a2 + 16;
    v10 = (char *)*((_QWORD *)a2 + 2);
    if ( v10 == (char *)a2 + 16 )
    {
LABEL_22:
      TpmResource::~TpmResource(a2);
      TpmFree(a2);
      return;
    }
    if ( *((char **)v10 + 1) == v9 )
    {
      v11 = (char **)*((_QWORD *)a2 + 3);
      if ( *v11 == v9 )
      {
        *v11 = v10;
        *((_QWORD *)v10 + 1) = v11;
        goto LABEL_22;
      }
    }
LABEL_24:
    __fastfail(3u);
  }
}

```

## disassembly

```asm
0x14001506c  test    rdx, rdx
0x14001506f  jz      locret_140015183
0x140015075  mov     [rsp+arg_0], rbx
0x14001507a  mov     [rsp+arg_8], rsi
0x14001507f  push    rdi
0x140015080  sub     rsp, 20h
0x140015084  lea     rax, [rcx+28h]
0x140015088  mov     sil, r8b
0x14001508b  mov     rbx, rdx
0x14001508e  mov     rdi, rcx
0x140015091  cmp     rdx, rax
0x140015094  jz      loc_140015174
0x14001509a  lea     rax, [rcx+88h]
0x1400150a1  cmp     rdx, rax
0x1400150a4  jz      loc_140015174
0x1400150aa  lea     rax, [rcx+0E8h]
0x1400150b1  cmp     rdx, rax
0x1400150b4  jz      loc_140015174
0x1400150ba  lea     rax, [rcx+148h]
0x1400150c1  cmp     rdx, rax
0x1400150c4  jz      loc_140015174
0x1400150ca  lea     rax, [rcx+1A8h]
0x1400150d1  cmp     rdx, rax
0x1400150d4  jz      loc_140015174
0x1400150da  lea     rax, [rcx+208h]
0x1400150e1  cmp     rdx, rax
0x1400150e4  jz      loc_140015174
0x1400150ea  lea     rax, [rcx+268h]
0x1400150f1  cmp     rdx, rax
0x1400150f4  jz      short loc_140015174
0x1400150f6  lea     rax, [rcx+2C8h]
0x1400150fd  cmp     rdx, rax
0x140015100  jz      short loc_140015174
0x140015102  mov     rax, [rdx+40h]
0x140015106  jmp     short loc_14001511F
0x140015108  test    sil, sil
0x14001510b  jz      short loc_140015124
0x14001510d  mov     r8b, 1; bool
0x140015110  mov     rdx, rax; struct TpmResource *
0x140015113  mov     rcx, rdi; this
0x140015116  call    ?DeleteResource@TpmResourceManager@@AEAAXPEAVTpmResource@@_N@Z; TpmResourceManager::DeleteResource(TpmResource *,bool)
0x14001511b  mov     rax, [rbx+40h]
0x14001511f  test    rax, rax
0x140015122  jnz     short loc_140015108
0x140015124  mov     rax, [rbx]
0x140015127  cmp     rax, rbx
0x14001512a  jz      short loc_140015142
0x14001512c  cmp     [rax+8], rbx
0x140015130  jnz     short loc_140015185
0x140015132  mov     rcx, [rbx+8]
0x140015136  cmp     [rcx], rbx
0x140015139  jnz     short loc_140015185
0x14001513b  mov     [rcx], rax
0x14001513e  mov     [rax+8], rcx
0x140015142  lea     rax, [rbx+10h]
0x140015146  mov     rcx, [rax]
0x140015149  cmp     rcx, rax
0x14001514c  jz      short loc_140015164
0x14001514e  cmp     [rcx+8], rax
0x140015152  jnz     short loc_140015185
0x140015154  mov     rdx, [rax+8]
0x140015158  cmp     [rdx], rax
0x14001515b  jnz     short loc_140015185
0x14001515d  mov     [rdx], rcx
0x140015160  mov     [rcx+8], rdx
0x140015164  mov     rcx, rbx; this
0x140015167  call    ??1TpmResource@@QEAA@XZ; TpmResource::~TpmResource(void)
0x14001516c  mov     rcx, rbx; void *
0x14001516f  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140015174  mov     rbx, [rsp+28h+arg_0]
0x140015179  mov     rsi, [rsp+28h+arg_8]
0x14001517e  add     rsp, 20h
0x140015182  pop     rdi
0x140015183  retn
0x140015185  mov     ecx, 3
0x14001518a  int     29h; Win8: RtlFailFast(ecx)
```
