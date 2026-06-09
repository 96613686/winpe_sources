# GetComponentInfoString(uchar,ulong,_BLB_BACKUP_COMPONENT_STATUS *,ushort * *)

- ea: `0x1400d2750`
- end: `0x1400d2bdf`
- name: `?GetComponentInfoString@@YAJEKPEAU_BLB_BACKUP_COMPONENT_STATUS@@PEAPEAG@Z`
- size: `1167`
- prototype: `__int64 __fastcall(unsigned __int8, unsigned int, struct _BLB_BACKUP_COMPONENT_STATUS *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400d4ff4`

## callees

- `0x140006ca8`
- `0x14000cbcc`
- `0x14001358c`
- `0x14008863c`
- `0x1400889f0`
- `0x1400d2750`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400d2aeb`
- `ole32!CoTaskMemFree` at `0x1400d2b1a`
- `ole32!CoTaskMemFree` at `0x1400d2b2f`
- `ole32!CoTaskMemFree` at `0x1400d2b9a`
- `ole32!CoTaskMemFree` at `0x1400d2ba8`
- `ole32!CoTaskMemFree` at `0x1400d2bbc`
- `ole32!CoTaskMemFree` at `0x1400d2aeb`
- `ole32!CoTaskMemFree` at `0x1400d2b1a`
- `ole32!CoTaskMemFree` at `0x1400d2b2f`
- `ole32!CoTaskMemFree` at `0x1400d2b9a`
- `ole32!CoTaskMemFree` at `0x1400d2ba8`
- `ole32!CoTaskMemFree` at `0x1400d2bbc`

## string_xrefs

- `0x1400d2833`: `wszComponentName`
- `0x1400d27a1`: `pwszComponentInfo`
- `0x1400d27c0`: `<ComponentInfo>`
- `0x1400d29f5`: `<ComponentInfoItem WriterId="{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}" InstanceId="{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}" Name="%ws" LogicalPath="%ws" Caption="%ws" AppName="%ws" hResult="%d" hDetailedResult="%d" IsFullBackup="%d" FullBackupReason="%d" Size="%I64u" DataTransferred="%I64u" TotalNoOfFiles="%I64u" />`
- `0x1400d2b73`: `</ComponentInfo>`

## pseudocode

```c
__int64 __fastcall GetComponentInfoString(
        char a1,
        unsigned int a2,
        struct _BLB_BACKUP_COMPONENT_STATUS *a3,
        unsigned __int16 **a4)
{
  unsigned __int16 *v4; // rsi
  unsigned __int16 **v5; // r15
  struct _BLB_BACKUP_COMPONENT_STATUS *v6; // r12
  unsigned int v7; // r13d
  int appended; // edi
  unsigned int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rax
  int v17; // esi
  __int64 v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // esi
  int v25; // r10d
  int v26; // r11d
  int v27; // ebx
  int v28; // edi
  int v29; // r14d
  int v30; // r15d
  int v31; // r12d
  int v32; // eax
  void *v33; // rbx
  unsigned __int16 *v34; // rbx
  unsigned __int16 *v35; // rcx
  __int64 v37; // [rsp+28h] [rbp-180h]
  __int64 v38; // [rsp+30h] [rbp-178h]
  __int64 v39; // [rsp+38h] [rbp-170h]
  __int64 v40; // [rsp+40h] [rbp-168h]
  __int64 v41; // [rsp+48h] [rbp-160h]
  __int64 v42; // [rsp+50h] [rbp-158h]
  __int64 v43; // [rsp+58h] [rbp-150h]
  __int64 v44; // [rsp+60h] [rbp-148h]
  __int64 v45; // [rsp+68h] [rbp-140h]
  __int64 v46; // [rsp+70h] [rbp-138h]
  __int64 v47; // [rsp+78h] [rbp-130h]
  __int64 v48; // [rsp+80h] [rbp-128h]
  __int64 v49; // [rsp+88h] [rbp-120h]
  __int64 v50; // [rsp+90h] [rbp-118h]
  __int64 v51; // [rsp+98h] [rbp-110h]
  __int64 v52; // [rsp+A0h] [rbp-108h]
  __int64 v53; // [rsp+A8h] [rbp-100h]
  __int64 v54; // [rsp+B0h] [rbp-F8h]
  __int64 v55; // [rsp+B8h] [rbp-F0h]
  __int64 v56; // [rsp+C0h] [rbp-E8h]
  __int64 v57; // [rsp+C8h] [rbp-E0h]
  __int64 v58; // [rsp+F0h] [rbp-B8h]
  __int64 v59; // [rsp+F8h] [rbp-B0h]
  __int64 v60; // [rsp+100h] [rbp-A8h]
  __int64 v61; // [rsp+108h] [rbp-A0h]
  unsigned int v62; // [rsp+128h] [rbp-80h]
  LPVOID pv; // [rsp+130h] [rbp-78h] BYREF
  unsigned __int16 *v64; // [rsp+138h] [rbp-70h] BYREF
  __int64 v65; // [rsp+140h] [rbp-68h]
  int v66; // [rsp+148h] [rbp-60h]
  unsigned __int16 *v67; // [rsp+150h] [rbp-58h]
  unsigned __int16 *v68; // [rsp+158h] [rbp-50h] BYREF
  int v69; // [rsp+160h] [rbp-48h]
  __int64 v70; // [rsp+168h] [rbp-40h]
  __int64 v71; // [rsp+170h] [rbp-38h]
  __int64 v72; // [rsp+178h] [rbp-30h]
  __int64 v73; // [rsp+180h] [rbp-28h]

  pv = 0;
  v4 = 0;
  v67 = 0;
  v68 = 0;
  v5 = a4;
  v64 = 0;
  v6 = a3;
  v7 = a2;
  if ( !a4 )
    BlbAssert("base\\stor\\blb\\blbevents\\publisher\\blbpublisher.cpp", 0x264u, "pwszComponentInfo");
  appended = BlbutilDuplicateString(L"<ComponentInfo>", (unsigned __int16 **)&pv, 0);
  if ( appended < 0 )
  {
    v33 = pv;
  }
  else
  {
    if ( !a1 )
    {
      v10 = 0;
      v11 = 0;
      v62 = 0;
      while ( 1 )
      {
        v66 = v11;
        if ( (unsigned int)v11 >= v7 )
          break;
        v65 = 144 * v11;
        v12 = *((_QWORD *)v6 + 18 * v11 + 14);
        v13 = *((_QWORD *)v6 + 18 * v11 + 15);
        v14 = *((_QWORD *)v6 + 18 * v11 + 16);
        v15 = *((_QWORD *)v6 + 18 * v11 + 13);
        v73 = v12;
        v72 = v13;
        v71 = v14;
        v70 = v15;
        if ( !v12 )
        {
          BlbAssert("base\\stor\\blb\\blbevents\\publisher\\blbpublisher.cpp", 0x277u, "wszComponentName");
          v10 = v62;
          v14 = v71;
          v13 = v72;
          v15 = v70;
          v12 = v73;
        }
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(v12 + 2 * v16) );
        v17 = v16 + v10;
        if ( v13 )
        {
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)(v13 + 2 * v18) );
        }
        else
        {
          LODWORD(v18) = 0;
        }
        if ( v14 )
        {
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)(v14 + 2 * v19) );
        }
        else
        {
          LODWORD(v19) = 0;
        }
        if ( !v15 )
        {
          BlbAssert("base\\stor\\blb\\blbevents\\publisher\\blbpublisher.cpp", 0x27Du, "wszAppName");
          v15 = v70;
        }
        v20 = -1;
        do
          ++v20;
        while ( *(_WORD *)(v15 + 2 * v20) );
        v62 = v18 + 438 + v19 + v17 + v20;
        appended = BlbutilMemalloc((void **)&v68, v62, 2u);
        if ( appended < 0 )
        {
          v4 = v68;
LABEL_37:
          v33 = pv;
LABEL_38:
          v35 = v67;
          goto LABEL_43;
        }
        v21 = *((unsigned __int8 *)v6 + v65 + 96);
        v22 = *((unsigned __int8 *)v6 + v65 + 95);
        v23 = *((unsigned __int8 *)v6 + v65 + 94);
        v24 = *((unsigned __int8 *)v6 + v65 + 89);
        v25 = *((unsigned __int8 *)v6 + v65 + 93);
        v26 = *((unsigned __int8 *)v6 + v65 + 92);
        v27 = *((unsigned __int8 *)v6 + v65 + 91);
        v28 = *((unsigned __int8 *)v6 + v65 + 90);
        v29 = *((unsigned __int8 *)v6 + v65 + 88);
        v30 = *(unsigned __int16 *)((char *)v6 + v65 + 86);
        v31 = *(unsigned __int16 *)((char *)v6 + v65 + 84);
        v69 = *((unsigned __int8 *)a3 + v65 + 79);
        LODWORD(v61) = *(_DWORD *)((char *)a3 + v65 + 100);
        LODWORD(v60) = v21;
        LODWORD(v59) = *(_DWORD *)((char *)a3 + v65 + 8);
        LODWORD(v58) = *(_DWORD *)((char *)a3 + v65 + 4);
        LODWORD(v57) = v22;
        LODWORD(v56) = v23;
        LODWORD(v55) = v25;
        LODWORD(v54) = v26;
        LODWORD(v53) = v27;
        LODWORD(v52) = v28;
        LODWORD(v51) = v24;
        v4 = v68;
        LODWORD(v50) = v29;
        LODWORD(v49) = v30;
        LODWORD(v48) = v31;
        v6 = a3;
        LODWORD(v47) = *(_DWORD *)((char *)a3 + v65 + 80);
        LODWORD(v46) = v69;
        LODWORD(v45) = *((unsigned __int8 *)a3 + v65 + 78);
        LODWORD(v44) = *((unsigned __int8 *)a3 + v65 + 77);
        LODWORD(v43) = *((unsigned __int8 *)a3 + v65 + 76);
        LODWORD(v42) = *((unsigned __int8 *)a3 + v65 + 75);
        LODWORD(v41) = *((unsigned __int8 *)a3 + v65 + 74);
        LODWORD(v40) = *((unsigned __int8 *)a3 + v65 + 73);
        LODWORD(v39) = *((unsigned __int8 *)a3 + v65 + 72);
        LODWORD(v38) = *(unsigned __int16 *)((char *)a3 + v65 + 70);
        LODWORD(v37) = *(unsigned __int16 *)((char *)a3 + v65 + 68);
        v32 = StringCchPrintfW(
                v68,
                v62,
                L"<ComponentInfoItem WriterId=\"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\" InstanceId=\"{%.8x-%."
                 "4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\" Name=\"%ws\" LogicalPath=\"%ws\" Caption=\"%ws\" AppName=\""
                 "%ws\" hResult=\"%d\" hDetailedResult=\"%d\" IsFullBackup=\"%d\" FullBackupReason=\"%d\" Size=\"%I64u\" "
                 "DataTransferred=\"%I64u\" TotalNoOfFiles=\"%I64u\" />",
                *(unsigned int *)((char *)a3 + v65 + 64),
                v37,
                v38,
                v39,
                v40,
                v41,
                v42,
                v43,
                v44,
                v45,
                v46,
                v47,
                v48,
                v49,
                v50,
                v51,
                v52,
                v53,
                v54,
                v55,
                v56,
                v57,
                v73,
                v72,
                v71,
                v70,
                v58,
                v59,
                v60,
                v61,
                *(_QWORD *)((char *)a3 + v65 + 16),
                *(_QWORD *)((char *)a3 + v65 + 40),
                *(_QWORD *)((char *)a3 + v65 + 48));
        v33 = pv;
        appended = v32;
        if ( v32 < 0 )
          goto LABEL_38;
        appended = BlbutilAppendString((const unsigned __int16 *)pv, v4, &v64);
        if ( appended < 0 )
          goto LABEL_42;
        if ( v33 )
        {
          CoTaskMemFree(v33);
          pv = 0;
        }
        v34 = v64;
        v67 = v64;
        appended = BlbutilDuplicateString(v64, (unsigned __int16 **)&pv, 0);
        if ( appended < 0 )
          goto LABEL_37;
        if ( v4 )
        {
          CoTaskMemFree(v4);
          v4 = 0;
          v68 = 0;
        }
        if ( v34 )
        {
          CoTaskMemFree(v34);
          v67 = 0;
          v64 = 0;
        }
        v10 = v62;
        v11 = (unsigned int)(v66 + 1);
        v7 = a2;
      }
      v5 = a4;
    }
    v33 = pv;
    appended = BlbutilAppendString((const unsigned __int16 *)pv, L"</ComponentInfo>", &v64);
    if ( appended < 0 )
    {
LABEL_42:
      v35 = v64;
    }
    else
    {
      v35 = 0;
      *v5 = v64;
    }
LABEL_43:
    if ( v35 )
      CoTaskMemFree(v35);
    if ( v4 )
      CoTaskMemFree(v4);
  }
  if ( v33 )
    CoTaskMemFree(v33);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400d2750  mov     rax, rsp
0x1400d2753  mov     [rax+8], rbx
0x1400d2757  mov     [rax+20h], r9
0x1400d275b  mov     [rax+18h], r8
0x1400d275f  mov     [rax+10h], edx
0x1400d2762  push    rbp
0x1400d2763  push    rsi
0x1400d2764  push    rdi
0x1400d2765  push    r12
0x1400d2767  push    r13
0x1400d2769  push    r14
0x1400d276b  push    r15
0x1400d276d  lea     rbp, [rax-18h]
0x1400d2771  sub     rsp, 180h
0x1400d2778  xor     ebx, ebx
0x1400d277a  mov     [rbp+10h+pv], 0
0x1400d2782  xor     esi, esi
0x1400d2784  mov     [rbp+10h+var_68], rbx
0x1400d2788  mov     [rbp+10h+var_60], rsi
0x1400d278c  mov     r15, r9
0x1400d278f  mov     [rbp+10h+var_80], rbx
0x1400d2793  mov     r12, r8
0x1400d2796  mov     r13d, edx
0x1400d2799  mov     r14b, cl
0x1400d279c  test    r9, r9
0x1400d279f  jnz     short loc_1400D27B9
0x1400d27a1  lea     r8, aPwszcomponenti; "pwszComponentInfo"
0x1400d27a8  mov     edx, 264h; unsigned int
0x1400d27ad  lea     rcx, aBaseStorBlbBlb_1; "base\\stor\\blb\\blbevents\\publisher\\"...
0x1400d27b4  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400d27b9  xor     r8d, r8d; unsigned __int64
0x1400d27bc  lea     rdx, [rbp+10h+pv]; unsigned __int16 **
0x1400d27c0  lea     rcx, aComponentinfo_0; "<ComponentInfo>"
0x1400d27c7  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400d27cc  mov     edi, eax
0x1400d27ce  test    eax, eax
0x1400d27d0  js      loc_1400D2BB0
0x1400d27d6  test    r14b, r14b
0x1400d27d9  jnz     loc_1400D2B65
0x1400d27df  xor     r14d, r14d
0x1400d27e2  mov     ecx, r14d
0x1400d27e5  mov     eax, r14d
0x1400d27e8  mov     dword ptr [rbp+10h+var_90], ecx
0x1400d27eb  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400d27ef  mov     [rbp+10h+var_70], eax
0x1400d27f2  cmp     eax, r13d
0x1400d27f5  jnb     loc_1400D2B5F
0x1400d27fb  lea     rax, [rax+rax*8]
0x1400d27ff  shl     rax, 4
0x1400d2803  mov     [rbp+10h+var_78], rax
0x1400d2807  mov     r10, [rax+r12+70h]
0x1400d280c  mov     r8, [rax+r12+78h]
0x1400d2811  mov     rdx, [rax+r12+80h]
0x1400d2819  mov     r9, [rax+r12+68h]
0x1400d281e  mov     [rbp+10h+var_38], r10
0x1400d2822  mov     [rbp+10h+var_40], r8
0x1400d2826  mov     [rbp+10h+var_48], rdx
0x1400d282a  mov     [rbp+10h+var_50], r9
0x1400d282e  test    r10, r10
0x1400d2831  jnz     short loc_1400D285E
0x1400d2833  lea     r8, aWszcomponentna; "wszComponentName"
0x1400d283a  mov     edx, 277h; unsigned int
0x1400d283f  lea     rcx, aBaseStorBlbBlb_1; "base\\stor\\blb\\blbevents\\publisher\\"...
0x1400d2846  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400d284b  mov     ecx, dword ptr [rbp+10h+var_90]
0x1400d284e  mov     rdx, [rbp+10h+var_48]
0x1400d2852  mov     r8, [rbp+10h+var_40]
0x1400d2856  mov     r9, [rbp+10h+var_50]
0x1400d285a  mov     r10, [rbp+10h+var_38]
0x1400d285e  mov     rax, r15
0x1400d2861  inc     rax
0x1400d2864  cmp     [r10+rax*2], r14w
0x1400d2869  jnz     short loc_1400D2861
0x1400d286b  lea     esi, [rax+rcx]
0x1400d286e  test    r8, r8
0x1400d2871  jz      short loc_1400D2882
0x1400d2873  mov     rdi, r15
0x1400d2876  inc     rdi
0x1400d2879  cmp     [r8+rdi*2], r14w
0x1400d287e  jnz     short loc_1400D2876
0x1400d2880  jmp     short loc_1400D2885
0x1400d2882  mov     edi, r14d
0x1400d2885  test    rdx, rdx
0x1400d2888  jz      short loc_1400D2899
0x1400d288a  mov     rbx, r15
0x1400d288d  inc     rbx
0x1400d2890  cmp     [rdx+rbx*2], r14w
0x1400d2895  jnz     short loc_1400D288D
0x1400d2897  jmp     short loc_1400D289C
0x1400d2899  mov     ebx, r14d
0x1400d289c  test    r9, r9
0x1400d289f  jnz     short loc_1400D28BD
0x1400d28a1  lea     r8, aWszappname; "wszAppName"
0x1400d28a8  mov     edx, 27Dh; unsigned int
0x1400d28ad  lea     rcx, aBaseStorBlbBlb_1; "base\\stor\\blb\\blbevents\\publisher\\"...
0x1400d28b4  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400d28b9  mov     r9, [rbp+10h+var_50]
0x1400d28bd  mov     rax, r15
0x1400d28c0  inc     rax
0x1400d28c3  cmp     [r9+rax*2], r14w
0x1400d28c8  jnz     short loc_1400D28C0
0x1400d28ca  add     eax, esi
0x1400d28cc  lea     rcx, [rbp+10h+var_60]; void **
0x1400d28d0  add     eax, ebx
0x1400d28d2  add     edi, 1B6h
0x1400d28d8  add     eax, edi
0x1400d28da  mov     r8d, 2; unsigned int
0x1400d28e0  mov     edx, eax; unsigned int
0x1400d28e2  mov     dword ptr [rbp+10h+var_90], eax
0x1400d28e5  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400d28ea  mov     edi, eax
0x1400d28ec  test    eax, eax
0x1400d28ee  js      loc_1400D2B51
0x1400d28f4  mov     rdx, [rbp+10h+var_78]
0x1400d28f8  mov     rax, [rbp+10h+arg_10]
0x1400d28fc  movzx   ecx, byte ptr [rdx+r12+60h]
0x1400d2902  movzx   r13d, byte ptr [rdx+rax+4Fh]
0x1400d2908  movzx   r8d, byte ptr [rdx+r12+5Fh]
0x1400d290e  movzx   r9d, byte ptr [rdx+r12+5Eh]
0x1400d2914  movzx   esi, byte ptr [rdx+r12+59h]
0x1400d291a  movzx   r10d, byte ptr [rdx+r12+5Dh]
0x1400d2920  movzx   r11d, byte ptr [rdx+r12+5Ch]
0x1400d2926  movzx   ebx, byte ptr [rdx+r12+5Bh]
0x1400d292c  movzx   edi, byte ptr [rdx+r12+5Ah]
0x1400d2932  movzx   r14d, byte ptr [rdx+r12+58h]
0x1400d2938  movzx   r15d, word ptr [rdx+r12+56h]
0x1400d293e  movzx   r12d, word ptr [rdx+r12+54h]
0x1400d2944  mov     edx, dword ptr [rbp+10h+var_90]; unsigned __int64
0x1400d2947  mov     [rbp+10h+var_58], r13d
0x1400d294b  mov     r13, rax
0x1400d294e  mov     rax, [rbp+10h+var_78]
0x1400d2952  mov     rax, [rax+r13+30h]
0x1400d2957  mov     [rsp+118h], rax
0x1400d295f  mov     rax, [rbp+10h+var_78]
0x1400d2963  mov     rax, [rax+r13+28h]
0x1400d2968  mov     [rsp+1B0h+var_A0], rax
0x1400d2970  mov     rax, [rbp+10h+var_78]
0x1400d2974  mov     rax, [rax+r13+10h]
0x1400d2979  mov     [rsp+1B0h+var_A8], rax
0x1400d2981  mov     rax, [rbp+10h+var_78]
0x1400d2985  mov     eax, [rax+r13+64h]
0x1400d298a  mov     dword ptr [rsp+1B0h+var_B0], eax
0x1400d2991  mov     rax, r13
0x1400d2994  mov     dword ptr [rsp+1B0h+var_B8], ecx
0x1400d299b  mov     rcx, [rbp+10h+var_78]
0x1400d299f  mov     eax, [rcx+rax+8]
0x1400d29a3  mov     dword ptr [rsp+1B0h+var_C0], eax
0x1400d29aa  mov     rax, r13
0x1400d29ad  mov     eax, [rcx+rax+4]
0x1400d29b1  mov     dword ptr [rsp+1B0h+var_C8], eax
0x1400d29b8  mov     rax, [rbp+10h+var_50]
0x1400d29bc  mov     qword ptr [rsp+1B0h+var_D0], rax
0x1400d29c4  mov     rax, [rbp+10h+var_48]
0x1400d29c8  mov     [rsp+1B0h+var_D8], rax
0x1400d29d0  mov     rax, [rbp+10h+var_40]
0x1400d29d4  mov     [rsp+1B0h+var_E0], rax
0x1400d29dc  mov     rax, [rbp+10h+var_38]
0x1400d29e0  mov     [rsp+1B0h+var_E8], rax
0x1400d29e8  mov     eax, [rcx+r13+50h]
0x1400d29ed  mov     dword ptr [rsp+1B0h+var_F0], r8d
0x1400d29f5  lea     r8, aComponentinfoi; "<ComponentInfoItem WriterId=\"{%.8x-%.4"...
0x1400d29fc  mov     dword ptr [rsp+1B0h+var_F8], r9d
0x1400d2a04  mov     dword ptr [rsp+1B0h+var_100], r10d
0x1400d2a0c  mov     dword ptr [rsp+1B0h+var_108], r11d
0x1400d2a14  mov     dword ptr [rsp+1B0h+var_110], ebx
0x1400d2a1b  mov     dword ptr [rsp+1B0h+var_118], edi
0x1400d2a22  mov     dword ptr [rsp+1B0h+var_120], esi
0x1400d2a29  mov     rsi, [rbp+10h+var_60]
0x1400d2a2d  mov     dword ptr [rsp+1B0h+var_128], r14d
0x1400d2a35  mov     dword ptr [rsp+1B0h+var_130], r15d
0x1400d2a3d  mov     dword ptr [rsp+1B0h+var_138], r12d
0x1400d2a42  mov     r12, r13
0x1400d2a45  mov     r13d, [rbp+10h+var_58]
0x1400d2a49  mov     dword ptr [rsp+1B0h+var_140], eax
0x1400d2a4d  mov     dword ptr [rsp+1B0h+var_148], r13d
0x1400d2a52  movzx   eax, byte ptr [rcx+r12+4Eh]
0x1400d2a58  mov     r9d, [rcx+r12+40h]
0x1400d2a5d  mov     dword ptr [rsp+1B0h+var_150], eax
0x1400d2a61  movzx   eax, byte ptr [rcx+r12+4Dh]
0x1400d2a67  mov     dword ptr [rsp+1B0h+var_158], eax
0x1400d2a6b  movzx   eax, byte ptr [rcx+r12+4Ch]
0x1400d2a71  mov     dword ptr [rsp+1B0h+var_160], eax
0x1400d2a75  movzx   eax, byte ptr [rcx+r12+4Bh]
0x1400d2a7b  mov     dword ptr [rsp+1B0h+var_168], eax
0x1400d2a7f  movzx   eax, byte ptr [rcx+r12+4Ah]
0x1400d2a85  mov     dword ptr [rsp+1B0h+var_170], eax
0x1400d2a89  movzx   eax, byte ptr [rcx+r12+49h]
0x1400d2a8f  mov     dword ptr [rsp+1B0h+var_178], eax
0x1400d2a93  movzx   eax, byte ptr [rcx+r12+48h]
0x1400d2a99  mov     dword ptr [rsp+1B0h+var_180], eax
0x1400d2a9d  movzx   eax, word ptr [rcx+r12+46h]
0x1400d2aa3  mov     dword ptr [rsp+1B0h+var_188], eax
0x1400d2aa7  movzx   eax, word ptr [rcx+r12+44h]
0x1400d2aad  mov     dword ptr [rsp+1B0h+var_190], eax
0x1400d2ab1  mov     rcx, rsi; unsigned __int16 *
0x1400d2ab4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400d2ab9  mov     rbx, [rbp+10h+pv]
0x1400d2abd  xor     r14d, r14d
0x1400d2ac0  mov     edi, eax
0x1400d2ac2  test    eax, eax
0x1400d2ac4  js      loc_1400D2B59
0x1400d2aca  lea     r8, [rbp+10h+var_80]; unsigned __int16 **
0x1400d2ace  mov     rdx, rsi; unsigned __int16 *
0x1400d2ad1  mov     rcx, rbx; unsigned __int16 *
0x1400d2ad4  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1400d2ad9  mov     edi, eax
0x1400d2adb  test    eax, eax
0x1400d2add  js      loc_1400D2B91
0x1400d2ae3  test    rbx, rbx
0x1400d2ae6  jz      short loc_1400D2AF5
0x1400d2ae8  mov     rcx, rbx; pv
0x1400d2aeb  call    cs:__imp_CoTaskMemFree
0x1400d2af1  mov     [rbp+10h+pv], r14
0x1400d2af5  mov     rbx, [rbp+10h+var_80]
0x1400d2af9  lea     rdx, [rbp+10h+pv]; unsigned __int16 **
0x1400d2afd  mov     rcx, rbx; unsigned __int16 *
0x1400d2b00  mov     [rbp+10h+var_68], rbx
0x1400d2b04  xor     r8d, r8d; unsigned __int64
0x1400d2b07  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400d2b0c  mov     edi, eax
0x1400d2b0e  test    eax, eax
0x1400d2b10  js      short loc_1400D2B55
0x1400d2b12  test    rsi, rsi
0x1400d2b15  jz      short loc_1400D2B27
0x1400d2b17  mov     rcx, rsi; pv
0x1400d2b1a  call    cs:__imp_CoTaskMemFree
0x1400d2b20  mov     rsi, r14
0x1400d2b23  mov     [rbp+10h+var_60], r14
0x1400d2b27  test    rbx, rbx
0x1400d2b2a  jz      short loc_1400D2B40
0x1400d2b2c  mov     rcx, rbx; pv
0x1400d2b2f  call    cs:__imp_CoTaskMemFree
0x1400d2b35  mov     rax, r14
0x1400d2b38  mov     [rbp+10h+var_68], rax
0x1400d2b3c  mov     [rbp+10h+var_80], rax
0x1400d2b40  mov     eax, [rbp+10h+var_70]
0x1400d2b43  mov     ecx, dword ptr [rbp+10h+var_90]
0x1400d2b46  inc     eax
0x1400d2b48  mov     r13d, [rbp+10h+arg_8]
0x1400d2b4c  jmp     loc_1400D27EB
0x1400d2b51  mov     rsi, [rbp+10h+var_60]
0x1400d2b55  mov     rbx, [rbp+10h+pv]
0x1400d2b59  mov     rcx, [rbp+10h+var_68]
0x1400d2b5d  jmp     short loc_1400D2B95
0x1400d2b5f  mov     r15, [rbp+10h+arg_18]
0x1400d2b63  jmp     short loc_1400D2B68
0x1400d2b65  xor     r14d, r14d
0x1400d2b68  mov     rbx, [rbp+10h+pv]
0x1400d2b6c  lea     r8, [rbp+10h+var_80]; unsigned __int16 **
0x1400d2b70  mov     rcx, rbx; unsigned __int16 *
0x1400d2b73  lea     rdx, aComponentinfo; "</ComponentInfo>"
0x1400d2b7a  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1400d2b7f  mov     edi, eax
0x1400d2b81  test    eax, eax
0x1400d2b83  js      short loc_1400D2B91
0x1400d2b85  mov     rax, [rbp+10h+var_80]
0x1400d2b89  mov     rcx, r14
0x1400d2b8c  mov     [r15], rax
0x1400d2b8f  jmp     short loc_1400D2B95
0x1400d2b91  mov     rcx, [rbp+10h+var_80]; pv
0x1400d2b95  test    rcx, rcx
0x1400d2b98  jz      short loc_1400D2BA0
0x1400d2b9a  call    cs:__imp_CoTaskMemFree
0x1400d2ba0  test    rsi, rsi
0x1400d2ba3  jz      short loc_1400D2BB4
0x1400d2ba5  mov     rcx, rsi; pv
0x1400d2ba8  call    cs:__imp_CoTaskMemFree
0x1400d2bae  jmp     short loc_1400D2BB4
0x1400d2bb0  mov     rbx, [rbp+10h+pv]
0x1400d2bb4  test    rbx, rbx
0x1400d2bb7  jz      short loc_1400D2BC2
0x1400d2bb9  mov     rcx, rbx; pv
0x1400d2bbc  call    cs:__imp_CoTaskMemFree
0x1400d2bc2  mov     rbx, [rsp+1B0h+arg_0]
0x1400d2bca  mov     eax, edi
0x1400d2bcc  add     rsp, 180h
0x1400d2bd3  pop     r15
0x1400d2bd5  pop     r14
0x1400d2bd7  pop     r13
0x1400d2bd9  pop     r12
0x1400d2bdb  pop     rdi
0x1400d2bdc  pop     rsi
0x1400d2bdd  pop     rbp
0x1400d2bde  retn
```
